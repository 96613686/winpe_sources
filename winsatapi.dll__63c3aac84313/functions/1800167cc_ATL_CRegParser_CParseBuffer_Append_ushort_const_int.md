# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x1800167cc`
- end: `0x18001688c`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `192`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800194d0`

## callees

- `0x1800167cc`
- `0x180016a1c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001685e`
- `msvcrt!memcpy_s` at `0x18001685e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180016821`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180016821`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::CParseBuffer::Append(
        ATL::CRegParser::CParseBuffer *this,
        const unsigned __int16 *a2,
        int a3)
{
  int v6; // ecx
  int v7; // ebx
  unsigned __int64 v8; // rax
  LPVOID v9; // rax
  int v10; // ecx
  errno_t v11; // eax

  v6 = *(_DWORD *)this + a3 + 1;
  if ( v6 > *(_DWORD *)this && v6 > a3 )
  {
    v7 = *((_DWORD *)this + 1);
    if ( v6 >= v7 )
    {
      while ( v6 >= v7 )
      {
        if ( v7 > 0x3FFFFFFF )
          return 0;
        v7 *= 2;
      }
      v8 = 2LL * (unsigned int)v7;
      if ( v8 > 0xFFFFFFFF )
        return 0;
      v9 = CoTaskMemRealloc(*((LPVOID *)this + 1), (unsigned int)v8);
      if ( !v9 )
        return 0;
      *((_QWORD *)this + 1) = v9;
      *((_DWORD *)this + 1) = v7;
    }
    if ( *(int *)this >= 0 && *(_DWORD *)this < v7 )
    {
      v10 = v7 - *(_DWORD *)this;
      if ( v10 <= v7 )
      {
        v11 = memcpy_s((void *const)(*((_QWORD *)this + 1) + 2LL * *(int *)this), 2LL * v10, a2, 2 * a3);
        ATL::AtlCrtErrorCheck(v11);
        *(_DWORD *)this += a3;
        *(_WORD *)(*((_QWORD *)this + 1) + 2LL * *(int *)this) = 0;
        return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800167cc  push    rbx
0x1800167ce  push    rbp
0x1800167cf  push    rsi
0x1800167d0  push    rdi
0x1800167d1  sub     rsp, 28h
0x1800167d5  mov     rdi, rcx
0x1800167d8  mov     esi, r8d
0x1800167db  lea     ecx, [r8+1]
0x1800167df  mov     rbp, rdx
0x1800167e2  add     ecx, [rdi]
0x1800167e4  cmp     ecx, [rdi]
0x1800167e6  jle     loc_180016881
0x1800167ec  cmp     ecx, r8d
0x1800167ef  jle     loc_180016881
0x1800167f5  mov     ebx, [rdi+4]
0x1800167f8  cmp     ecx, ebx
0x1800167fa  jl      short loc_180016833
0x1800167fc  cmp     ecx, ebx
0x1800167fe  jl      short loc_18001680C
0x180016800  cmp     ebx, 3FFFFFFFh
0x180016806  jg      short loc_180016881
0x180016808  add     ebx, ebx
0x18001680a  jmp     short loc_1800167FC
0x18001680c  mov     eax, ebx
0x18001680e  mov     ecx, 0FFFFFFFFh
0x180016813  add     rax, rax
0x180016816  cmp     rax, rcx
0x180016819  ja      short loc_180016881
0x18001681b  mov     rcx, [rdi+8]; pv
0x18001681f  mov     edx, eax; cb
0x180016821  call    cs:__imp_CoTaskMemRealloc
0x180016827  test    rax, rax
0x18001682a  jz      short loc_180016881
0x18001682c  mov     [rdi+8], rax
0x180016830  mov     [rdi+4], ebx
0x180016833  cmp     dword ptr [rdi], 0
0x180016836  jl      short loc_180016881
0x180016838  cmp     [rdi], ebx
0x18001683a  jge     short loc_180016881
0x18001683c  mov     ecx, ebx
0x18001683e  sub     ecx, [rdi]
0x180016840  cmp     ecx, ebx
0x180016842  jg      short loc_180016881
0x180016844  movsxd  rdx, ecx
0x180016847  lea     eax, [rsi+rsi]
0x18001684a  movsxd  rcx, dword ptr [rdi]
0x18001684d  add     rdx, rdx; DestinationSize
0x180016850  movsxd  r9, eax; SourceSize
0x180016853  mov     r8, rbp; Source
0x180016856  mov     rax, [rdi+8]
0x18001685a  lea     rcx, [rax+rcx*2]; Destination
0x18001685e  call    cs:__imp_memcpy_s
0x180016864  mov     ecx, eax; int
0x180016866  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001686b  add     [rdi], esi
0x18001686d  movsxd  rdx, dword ptr [rdi]
0x180016870  xor     eax, eax
0x180016872  mov     rcx, [rdi+8]
0x180016876  mov     [rcx+rdx*2], ax
0x18001687a  mov     eax, 1
0x18001687f  jmp     short loc_180016883
0x180016881  xor     eax, eax
0x180016883  add     rsp, 28h
0x180016887  pop     rdi
0x180016888  pop     rsi
0x180016889  pop     rbp
0x18001688a  pop     rbx
0x18001688b  retn
```
