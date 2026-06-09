# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180002d2c`
- end: `0x180002de2`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `182`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003394`

## callees

- `0x180002d2c`
- `0x180004a94`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180002d7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180002d7f`

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
0x180002d2c  push    rbx
0x180002d2e  push    rbp
0x180002d2f  push    rsi
0x180002d30  push    rdi
0x180002d31  sub     rsp, 28h
0x180002d35  mov     rdi, rcx
0x180002d38  mov     esi, r8d
0x180002d3b  lea     ecx, [r8+1]
0x180002d3f  mov     rbp, rdx
0x180002d42  add     ecx, [rdi]
0x180002d44  cmp     ecx, [rdi]
0x180002d46  jle     loc_180002DD7
0x180002d4c  cmp     ecx, r8d
0x180002d4f  jle     loc_180002DD7
0x180002d55  mov     ebx, [rdi+4]
0x180002d58  cmp     ecx, ebx
0x180002d5a  jl      short loc_180002D91
0x180002d5c  cmp     ebx, 3FFFFFFFh
0x180002d62  jg      short loc_180002DD7
0x180002d64  add     ebx, ebx
0x180002d66  cmp     ecx, ebx
0x180002d68  jge     short loc_180002D5C
0x180002d6a  mov     eax, ebx
0x180002d6c  mov     ecx, 0FFFFFFFFh
0x180002d71  add     rax, rax
0x180002d74  cmp     rax, rcx
0x180002d77  ja      short loc_180002DD7
0x180002d79  mov     rcx, [rdi+8]; pv
0x180002d7d  mov     edx, eax; cb
0x180002d7f  call    cs:__imp_CoTaskMemRealloc
0x180002d85  test    rax, rax
0x180002d88  jz      short loc_180002DD7
0x180002d8a  mov     [rdi+8], rax
0x180002d8e  mov     [rdi+4], ebx
0x180002d91  cmp     dword ptr [rdi], 0
0x180002d94  jl      short loc_180002DD7
0x180002d96  cmp     [rdi], ebx
0x180002d98  jge     short loc_180002DD7
0x180002d9a  mov     ecx, ebx
0x180002d9c  sub     ecx, [rdi]
0x180002d9e  cmp     ecx, ebx
0x180002da0  jg      short loc_180002DD7
0x180002da2  movsxd  rdx, ecx
0x180002da5  lea     eax, [rsi+rsi]
0x180002da8  movsxd  rcx, dword ptr [rdi]
0x180002dab  add     rdx, rdx; void *
0x180002dae  movsxd  r9, eax; void *
0x180002db1  mov     r8, rbp; unsigned __int64
0x180002db4  mov     rax, [rdi+8]
0x180002db8  lea     rcx, [rax+rcx*2]; this
0x180002dbc  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x180002dc1  add     [rdi], esi
0x180002dc3  movsxd  rdx, dword ptr [rdi]
0x180002dc6  xor     eax, eax
0x180002dc8  mov     rcx, [rdi+8]
0x180002dcc  mov     [rcx+rdx*2], ax
0x180002dd0  mov     eax, 1
0x180002dd5  jmp     short loc_180002DD9
0x180002dd7  xor     eax, eax
0x180002dd9  add     rsp, 28h
0x180002ddd  pop     rdi
0x180002dde  pop     rsi
0x180002ddf  pop     rbp
0x180002de0  pop     rbx
0x180002de1  retn
```
