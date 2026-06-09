# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180004288`
- end: `0x18000433f`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `183`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000cea4`

## callees

- `0x180004288`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180004318`
- `msvcrt!memcpy_s` at `0x180004318`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800042db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800042db`

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
0x180004288  push    rbx
0x18000428a  push    rbp
0x18000428b  push    rsi
0x18000428c  push    rdi
0x18000428d  sub     rsp, 28h
0x180004291  mov     rdi, rcx
0x180004294  mov     esi, r8d
0x180004297  lea     ecx, [r8+1]
0x18000429b  mov     rbp, rdx
0x18000429e  add     ecx, [rdi]
0x1800042a0  cmp     ecx, [rdi]
0x1800042a2  jle     loc_180004334
0x1800042a8  cmp     ecx, r8d
0x1800042ab  jle     loc_180004334
0x1800042b1  mov     ebx, [rdi+4]
0x1800042b4  cmp     ecx, ebx
0x1800042b6  jl      short loc_1800042ED
0x1800042b8  cmp     ebx, 3FFFFFFFh
0x1800042be  jg      short loc_180004334
0x1800042c0  add     ebx, ebx
0x1800042c2  cmp     ecx, ebx
0x1800042c4  jge     short loc_1800042B8
0x1800042c6  mov     eax, ebx
0x1800042c8  mov     ecx, 0FFFFFFFFh
0x1800042cd  add     rax, rax
0x1800042d0  cmp     rax, rcx
0x1800042d3  ja      short loc_180004334
0x1800042d5  mov     rcx, [rdi+8]; pv
0x1800042d9  mov     edx, eax; cb
0x1800042db  call    cs:__imp_CoTaskMemRealloc
0x1800042e1  test    rax, rax
0x1800042e4  jz      short loc_180004334
0x1800042e6  mov     [rdi+8], rax
0x1800042ea  mov     [rdi+4], ebx
0x1800042ed  cmp     dword ptr [rdi], 0
0x1800042f0  jl      short loc_180004334
0x1800042f2  cmp     [rdi], ebx
0x1800042f4  jge     short loc_180004334
0x1800042f6  mov     ecx, ebx
0x1800042f8  sub     ecx, [rdi]
0x1800042fa  cmp     ecx, ebx
0x1800042fc  jg      short loc_180004334
0x1800042fe  movsxd  rdx, ecx
0x180004301  lea     eax, [rsi+rsi]
0x180004304  movsxd  rcx, dword ptr [rdi]
0x180004307  add     rdx, rdx; DestinationSize
0x18000430a  movsxd  r9, eax; SourceSize
0x18000430d  mov     r8, rbp; Source
0x180004310  mov     rax, [rdi+8]
0x180004314  lea     rcx, [rax+rcx*2]; Destination
0x180004318  call    cs:__imp_memcpy_s
0x18000431e  add     [rdi], esi
0x180004320  movsxd  rdx, dword ptr [rdi]
0x180004323  xor     eax, eax
0x180004325  mov     rcx, [rdi+8]
0x180004329  mov     [rcx+rdx*2], ax
0x18000432d  mov     eax, 1
0x180004332  jmp     short loc_180004336
0x180004334  xor     eax, eax
0x180004336  add     rsp, 28h
0x18000433a  pop     rdi
0x18000433b  pop     rsi
0x18000433c  pop     rbp
0x18000433d  pop     rbx
0x18000433e  retn
```
