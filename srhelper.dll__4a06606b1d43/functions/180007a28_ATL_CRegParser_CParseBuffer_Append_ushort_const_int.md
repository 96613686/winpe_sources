# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180007a28`
- end: `0x180007adf`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `183`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800088ac`

## callees

- `0x180007a28`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180007ab8`
- `msvcrt!memcpy_s` at `0x180007ab8`
- `ole32!CoTaskMemRealloc` at `0x180007a7b`
- `ole32!CoTaskMemRealloc` at `0x180007a7b`

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
0x180007a28  push    rbx
0x180007a2a  push    rbp
0x180007a2b  push    rsi
0x180007a2c  push    rdi
0x180007a2d  sub     rsp, 28h
0x180007a31  mov     rdi, rcx
0x180007a34  mov     esi, r8d
0x180007a37  lea     ecx, [r8+1]
0x180007a3b  mov     rbp, rdx
0x180007a3e  add     ecx, [rdi]
0x180007a40  cmp     ecx, [rdi]
0x180007a42  jle     loc_180007AD4
0x180007a48  cmp     ecx, r8d
0x180007a4b  jle     loc_180007AD4
0x180007a51  mov     ebx, [rdi+4]
0x180007a54  cmp     ecx, ebx
0x180007a56  jl      short loc_180007A8D
0x180007a58  cmp     ebx, 3FFFFFFFh
0x180007a5e  jg      short loc_180007AD4
0x180007a60  add     ebx, ebx
0x180007a62  cmp     ecx, ebx
0x180007a64  jge     short loc_180007A58
0x180007a66  mov     eax, ebx
0x180007a68  mov     ecx, 0FFFFFFFFh
0x180007a6d  add     rax, rax
0x180007a70  cmp     rax, rcx
0x180007a73  ja      short loc_180007AD4
0x180007a75  mov     rcx, [rdi+8]; pv
0x180007a79  mov     edx, eax; cb
0x180007a7b  call    cs:__imp_CoTaskMemRealloc
0x180007a81  test    rax, rax
0x180007a84  jz      short loc_180007AD4
0x180007a86  mov     [rdi+8], rax
0x180007a8a  mov     [rdi+4], ebx
0x180007a8d  cmp     dword ptr [rdi], 0
0x180007a90  jl      short loc_180007AD4
0x180007a92  cmp     [rdi], ebx
0x180007a94  jge     short loc_180007AD4
0x180007a96  mov     ecx, ebx
0x180007a98  sub     ecx, [rdi]
0x180007a9a  cmp     ecx, ebx
0x180007a9c  jg      short loc_180007AD4
0x180007a9e  movsxd  rdx, ecx
0x180007aa1  lea     eax, [rsi+rsi]
0x180007aa4  movsxd  rcx, dword ptr [rdi]
0x180007aa7  add     rdx, rdx; DestinationSize
0x180007aaa  movsxd  r9, eax; SourceSize
0x180007aad  mov     r8, rbp; Source
0x180007ab0  mov     rax, [rdi+8]
0x180007ab4  lea     rcx, [rax+rcx*2]; Destination
0x180007ab8  call    cs:__imp_memcpy_s
0x180007abe  add     [rdi], esi
0x180007ac0  movsxd  rdx, dword ptr [rdi]
0x180007ac3  xor     eax, eax
0x180007ac5  mov     rcx, [rdi+8]
0x180007ac9  mov     [rcx+rdx*2], ax
0x180007acd  mov     eax, 1
0x180007ad2  jmp     short loc_180007AD6
0x180007ad4  xor     eax, eax
0x180007ad6  add     rsp, 28h
0x180007ada  pop     rdi
0x180007adb  pop     rsi
0x180007adc  pop     rbp
0x180007add  pop     rbx
0x180007ade  retn
```
