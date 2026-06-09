# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x14000295c`
- end: `0x140002a12`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `182`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140003f2c`

## callees

- `0x14000295c`
- `0x140005bb4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1400029af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1400029af`

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
0x14000295c  push    rbx
0x14000295e  push    rbp
0x14000295f  push    rsi
0x140002960  push    rdi
0x140002961  sub     rsp, 28h
0x140002965  mov     rdi, rcx
0x140002968  mov     esi, r8d
0x14000296b  lea     ecx, [r8+1]
0x14000296f  mov     rbp, rdx
0x140002972  add     ecx, [rdi]
0x140002974  cmp     ecx, [rdi]
0x140002976  jle     loc_140002A07
0x14000297c  cmp     ecx, r8d
0x14000297f  jle     loc_140002A07
0x140002985  mov     ebx, [rdi+4]
0x140002988  cmp     ecx, ebx
0x14000298a  jl      short loc_1400029C1
0x14000298c  cmp     ebx, 3FFFFFFFh
0x140002992  jg      short loc_140002A07
0x140002994  add     ebx, ebx
0x140002996  cmp     ecx, ebx
0x140002998  jge     short loc_14000298C
0x14000299a  mov     eax, ebx
0x14000299c  mov     ecx, 0FFFFFFFFh
0x1400029a1  add     rax, rax
0x1400029a4  cmp     rax, rcx
0x1400029a7  ja      short loc_140002A07
0x1400029a9  mov     rcx, [rdi+8]; pv
0x1400029ad  mov     edx, eax; cb
0x1400029af  call    cs:__imp_CoTaskMemRealloc
0x1400029b5  test    rax, rax
0x1400029b8  jz      short loc_140002A07
0x1400029ba  mov     [rdi+8], rax
0x1400029be  mov     [rdi+4], ebx
0x1400029c1  cmp     dword ptr [rdi], 0
0x1400029c4  jl      short loc_140002A07
0x1400029c6  cmp     [rdi], ebx
0x1400029c8  jge     short loc_140002A07
0x1400029ca  mov     ecx, ebx
0x1400029cc  sub     ecx, [rdi]
0x1400029ce  cmp     ecx, ebx
0x1400029d0  jg      short loc_140002A07
0x1400029d2  movsxd  rdx, ecx
0x1400029d5  lea     eax, [rsi+rsi]
0x1400029d8  movsxd  rcx, dword ptr [rdi]
0x1400029db  add     rdx, rdx; void *
0x1400029de  movsxd  r9, eax; void *
0x1400029e1  mov     r8, rbp; unsigned __int64
0x1400029e4  mov     rax, [rdi+8]
0x1400029e8  lea     rcx, [rax+rcx*2]; this
0x1400029ec  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x1400029f1  add     [rdi], esi
0x1400029f3  movsxd  rdx, dword ptr [rdi]
0x1400029f6  xor     eax, eax
0x1400029f8  mov     rcx, [rdi+8]
0x1400029fc  mov     [rcx+rdx*2], ax
0x140002a00  mov     eax, 1
0x140002a05  jmp     short loc_140002A09
0x140002a07  xor     eax, eax
0x140002a09  add     rsp, 28h
0x140002a0d  pop     rdi
0x140002a0e  pop     rsi
0x140002a0f  pop     rbp
0x140002a10  pop     rbx
0x140002a11  retn
```
