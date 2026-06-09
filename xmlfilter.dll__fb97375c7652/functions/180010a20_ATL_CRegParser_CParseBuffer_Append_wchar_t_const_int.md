# ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)

- ea: `0x180010a20`
- end: `0x180010ad6`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z`
- size: `182`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011e40`

## callees

- `0x180010a20`
- `0x1800137f4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180010a73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180010a73`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::CParseBuffer::Append(
        ATL::CRegParser::CParseBuffer *this,
        const wchar_t *a2,
        int a3)
{
  int v6; // ecx
  int v7; // ebx
  unsigned __int64 v8; // rax
  LPVOID v9; // rax
  int v10; // ecx
  unsigned __int64 v12; // [rsp+20h] [rbp-28h]

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
          ATL::Checked::memcpy_s(
            (ATL::Checked *)(*((_QWORD *)this + 1) + 2LL * *(int *)this),
            (void *)(2LL * v10),
            (unsigned __int64)a2,
            (const void *)(2 * a3),
            v12);
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
0x180010a20  push    rbx
0x180010a22  push    rbp
0x180010a23  push    rsi
0x180010a24  push    rdi
0x180010a25  sub     rsp, 28h
0x180010a29  mov     rdi, rcx
0x180010a2c  mov     esi, r8d
0x180010a2f  lea     ecx, [r8+1]
0x180010a33  mov     rbp, rdx
0x180010a36  add     ecx, [rdi]
0x180010a38  cmp     ecx, [rdi]
0x180010a3a  jle     loc_180010ACB
0x180010a40  cmp     ecx, r8d
0x180010a43  jle     loc_180010ACB
0x180010a49  mov     ebx, [rdi+4]
0x180010a4c  cmp     ecx, ebx
0x180010a4e  jl      short loc_180010A85
0x180010a50  cmp     ebx, 3FFFFFFFh
0x180010a56  jg      short loc_180010ACB
0x180010a58  add     ebx, ebx
0x180010a5a  cmp     ecx, ebx
0x180010a5c  jge     short loc_180010A50
0x180010a5e  mov     eax, ebx
0x180010a60  mov     ecx, 0FFFFFFFFh
0x180010a65  add     rax, rax
0x180010a68  cmp     rax, rcx
0x180010a6b  ja      short loc_180010ACB
0x180010a6d  mov     rcx, [rdi+8]; pv
0x180010a71  mov     edx, eax; cb
0x180010a73  call    cs:__imp_CoTaskMemRealloc
0x180010a79  test    rax, rax
0x180010a7c  jz      short loc_180010ACB
0x180010a7e  mov     [rdi+8], rax
0x180010a82  mov     [rdi+4], ebx
0x180010a85  cmp     dword ptr [rdi], 0
0x180010a88  jl      short loc_180010ACB
0x180010a8a  cmp     [rdi], ebx
0x180010a8c  jge     short loc_180010ACB
0x180010a8e  mov     ecx, ebx
0x180010a90  sub     ecx, [rdi]
0x180010a92  cmp     ecx, ebx
0x180010a94  jg      short loc_180010ACB
0x180010a96  movsxd  rdx, ecx
0x180010a99  lea     eax, [rsi+rsi]
0x180010a9c  movsxd  rcx, dword ptr [rdi]
0x180010a9f  add     rdx, rdx; void *
0x180010aa2  movsxd  r9, eax; void *
0x180010aa5  mov     r8, rbp; unsigned __int64
0x180010aa8  mov     rax, [rdi+8]
0x180010aac  lea     rcx, [rax+rcx*2]; this
0x180010ab0  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x180010ab5  add     [rdi], esi
0x180010ab7  movsxd  rdx, dword ptr [rdi]
0x180010aba  xor     eax, eax
0x180010abc  mov     rcx, [rdi+8]
0x180010ac0  mov     [rcx+rdx*2], ax
0x180010ac4  mov     eax, 1
0x180010ac9  jmp     short loc_180010ACD
0x180010acb  xor     eax, eax
0x180010acd  add     rsp, 28h
0x180010ad1  pop     rdi
0x180010ad2  pop     rsi
0x180010ad3  pop     rbp
0x180010ad4  pop     rbx
0x180010ad5  retn
```
