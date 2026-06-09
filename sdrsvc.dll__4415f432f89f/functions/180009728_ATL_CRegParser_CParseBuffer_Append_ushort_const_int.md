# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180009728`
- end: `0x1800097df`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `183`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b2d0`

## callees

- `0x180009728`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800097b8`
- `msvcrt!memcpy_s` at `0x1800097b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000977b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000977b`

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

  v6 = *(_DWORD *)this + a3 + 1;
  if ( v6 > *(_DWORD *)this && v6 > a3 )
  {
    v7 = *((_DWORD *)this + 1);
    if ( v6 < v7 )
    {
LABEL_9:
      if ( *(int *)this >= 0 && *(_DWORD *)this < v7 )
      {
        v10 = v7 - *(_DWORD *)this;
        if ( v10 <= v7 )
        {
          memcpy_s((void *const)(*((_QWORD *)this + 1) + 2LL * *(int *)this), 2LL * v10, a2, 2 * a3);
          *(_DWORD *)this += a3;
          *(_WORD *)(*((_QWORD *)this + 1) + 2LL * *(int *)this) = 0;
          return 1;
        }
      }
    }
    else
    {
      while ( v7 <= 0x3FFFFFFF )
      {
        v7 *= 2;
        if ( v6 < v7 )
        {
          v8 = 2LL * (unsigned int)v7;
          if ( v8 <= 0xFFFFFFFF )
          {
            v9 = CoTaskMemRealloc(*((LPVOID *)this + 1), (unsigned int)v8);
            if ( v9 )
            {
              *((_QWORD *)this + 1) = v9;
              *((_DWORD *)this + 1) = v7;
              goto LABEL_9;
            }
          }
          return 0;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180009728  push    rbx
0x18000972a  push    rbp
0x18000972b  push    rsi
0x18000972c  push    rdi
0x18000972d  sub     rsp, 28h
0x180009731  mov     rdi, rcx
0x180009734  mov     esi, r8d
0x180009737  lea     ecx, [r8+1]
0x18000973b  mov     rbp, rdx
0x18000973e  add     ecx, [rdi]
0x180009740  cmp     ecx, [rdi]
0x180009742  jle     loc_1800097D4
0x180009748  cmp     ecx, r8d
0x18000974b  jle     loc_1800097D4
0x180009751  mov     ebx, [rdi+4]
0x180009754  cmp     ecx, ebx
0x180009756  jl      short loc_18000978D
0x180009758  cmp     ebx, 3FFFFFFFh
0x18000975e  jg      short loc_1800097D4
0x180009760  add     ebx, ebx
0x180009762  cmp     ecx, ebx
0x180009764  jge     short loc_180009758
0x180009766  mov     eax, ebx
0x180009768  mov     ecx, 0FFFFFFFFh
0x18000976d  add     rax, rax
0x180009770  cmp     rax, rcx
0x180009773  ja      short loc_1800097D4
0x180009775  mov     rcx, [rdi+8]; pv
0x180009779  mov     edx, eax; cb
0x18000977b  call    cs:__imp_CoTaskMemRealloc
0x180009781  test    rax, rax
0x180009784  jz      short loc_1800097D4
0x180009786  mov     [rdi+8], rax
0x18000978a  mov     [rdi+4], ebx
0x18000978d  cmp     dword ptr [rdi], 0
0x180009790  jl      short loc_1800097D4
0x180009792  cmp     [rdi], ebx
0x180009794  jge     short loc_1800097D4
0x180009796  mov     ecx, ebx
0x180009798  sub     ecx, [rdi]
0x18000979a  cmp     ecx, ebx
0x18000979c  jg      short loc_1800097D4
0x18000979e  movsxd  rdx, ecx
0x1800097a1  lea     eax, [rsi+rsi]
0x1800097a4  movsxd  rcx, dword ptr [rdi]
0x1800097a7  add     rdx, rdx; DestinationSize
0x1800097aa  movsxd  r9, eax; SourceSize
0x1800097ad  mov     r8, rbp; Source
0x1800097b0  mov     rax, [rdi+8]
0x1800097b4  lea     rcx, [rax+rcx*2]; Destination
0x1800097b8  call    cs:__imp_memcpy_s
0x1800097be  add     [rdi], esi
0x1800097c0  movsxd  rdx, dword ptr [rdi]
0x1800097c3  xor     eax, eax
0x1800097c5  mov     rcx, [rdi+8]
0x1800097c9  mov     [rcx+rdx*2], ax
0x1800097cd  mov     eax, 1
0x1800097d2  jmp     short loc_1800097D6
0x1800097d4  xor     eax, eax
0x1800097d6  add     rsp, 28h
0x1800097da  pop     rdi
0x1800097db  pop     rsi
0x1800097dc  pop     rbp
0x1800097dd  pop     rbx
0x1800097de  retn
```
