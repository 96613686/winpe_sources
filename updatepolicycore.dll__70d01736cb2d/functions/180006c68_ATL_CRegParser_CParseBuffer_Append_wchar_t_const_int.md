# ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)

- ea: `0x180006c68`
- end: `0x180006d34`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z`
- size: `204`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006d3c`

## callees

- `0x180006bdc`
- `0x180006c68`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180006cc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180006cc8`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::CParseBuffer::Append(
        ATL::CRegParser::CParseBuffer *this,
        const wchar_t *a2,
        int a3)
{
  __int64 v4; // rdi
  int v6; // ecx
  int v7; // eax
  unsigned __int64 v8; // rdx
  LPVOID v9; // rax
  int v10; // ecx
  int v11; // eax
  unsigned __int64 v13; // [rsp+20h] [rbp-8h]

  v4 = a3;
  v6 = *(_DWORD *)this + a3 + 1;
  if ( v6 > *(_DWORD *)this && v6 > a3 )
  {
    v7 = *((_DWORD *)this + 1);
    if ( v6 < v7 )
    {
LABEL_9:
      if ( *(int *)this >= 0 )
      {
        v10 = *((_DWORD *)this + 1);
        if ( *(_DWORD *)this < v10 )
        {
          v11 = v10 - *(_DWORD *)this;
          if ( v11 <= v10 )
          {
            ATL::Checked::memcpy_s(
              (ATL::Checked *)(*((_QWORD *)this + 1) + 2LL * *(int *)this),
              (void *)(2LL * v11),
              (unsigned __int64)a2,
              (const void *)(2 * v4),
              v13);
            *(_DWORD *)this += v4;
            *(_WORD *)(*((_QWORD *)this + 1) + 2LL * *(int *)this) = 0;
            return 1;
          }
        }
      }
    }
    else
    {
      while ( v7 <= 0x3FFFFFFF )
      {
        v7 *= 2;
        *((_DWORD *)this + 1) = v7;
        if ( v6 < v7 )
        {
          v8 = 2LL * (unsigned int)v7;
          if ( v8 <= 0xFFFFFFFF )
          {
            v9 = CoTaskMemRealloc(*((LPVOID *)this + 1), (unsigned int)v8);
            if ( v9 )
            {
              *((_QWORD *)this + 1) = v9;
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
0x180006c68  mov     [rsp+arg_0], rbx
0x180006c6d  mov     [rsp+arg_8], rbp
0x180006c72  mov     [rsp+arg_10], rsi
0x180006c77  push    rdi; unsigned __int64
0x180006c78  sub     rsp, 20h
0x180006c7c  mov     rbx, rcx
0x180006c7f  movsxd  rdi, r8d
0x180006c82  mov     rsi, rdx
0x180006c85  lea     ecx, [rdi+1]
0x180006c88  add     ecx, [rbx]
0x180006c8a  cmp     ecx, [rbx]
0x180006c8c  jle     loc_180006D1D
0x180006c92  cmp     ecx, edi
0x180006c94  jle     loc_180006D1D
0x180006c9a  mov     eax, [rbx+4]
0x180006c9d  xor     ebp, ebp
0x180006c9f  cmp     ecx, eax
0x180006ca1  jl      short loc_180006CD7
0x180006ca3  cmp     eax, 3FFFFFFFh
0x180006ca8  jg      short loc_180006D1D
0x180006caa  add     eax, eax
0x180006cac  mov     [rbx+4], eax
0x180006caf  cmp     ecx, eax
0x180006cb1  jge     short loc_180006CA3
0x180006cb3  mov     edx, eax
0x180006cb5  mov     eax, 0FFFFFFFFh
0x180006cba  add     rdx, rdx
0x180006cbd  cmp     rdx, rax
0x180006cc0  ja      short loc_180006D1D
0x180006cc2  mov     rcx, [rbx+8]; pv
0x180006cc6  mov     edx, edx; cb
0x180006cc8  call    cs:__imp_CoTaskMemRealloc
0x180006cce  test    rax, rax
0x180006cd1  jz      short loc_180006D1D
0x180006cd3  mov     [rbx+8], rax
0x180006cd7  cmp     [rbx], ebp
0x180006cd9  jl      short loc_180006D1D
0x180006cdb  mov     ecx, [rbx+4]
0x180006cde  cmp     [rbx], ecx
0x180006ce0  jge     short loc_180006D1D
0x180006ce2  mov     eax, ecx
0x180006ce4  sub     eax, [rbx]
0x180006ce6  cmp     eax, ecx
0x180006ce8  jg      short loc_180006D1D
0x180006cea  movsxd  rcx, dword ptr [rbx]
0x180006ced  mov     r9, rdi
0x180006cf0  movsxd  rdx, eax
0x180006cf3  add     r9, r9; void *
0x180006cf6  mov     rax, [rbx+8]
0x180006cfa  add     rdx, rdx; void *
0x180006cfd  mov     r8, rsi; unsigned __int64
0x180006d00  lea     rcx, [rax+rcx*2]; this
0x180006d04  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x180006d09  add     [rbx], edi
0x180006d0b  mov     rax, [rbx+8]
0x180006d0f  movsxd  rcx, dword ptr [rbx]
0x180006d12  mov     [rax+rcx*2], bp
0x180006d16  mov     eax, 1
0x180006d1b  jmp     short loc_180006D1F
0x180006d1d  xor     eax, eax
0x180006d1f  mov     rbx, [rsp+28h+arg_0]
0x180006d24  mov     rbp, [rsp+28h+arg_8]
0x180006d29  mov     rsi, [rsp+28h+arg_10]
0x180006d2e  add     rsp, 20h
0x180006d32  pop     rdi
0x180006d33  retn
```
