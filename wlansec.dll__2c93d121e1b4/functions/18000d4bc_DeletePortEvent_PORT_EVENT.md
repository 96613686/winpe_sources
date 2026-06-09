# DeletePortEvent(PORT_EVENT * *)

- ea: `0x18000d4bc`
- end: `0x18000d5dd`
- name: `?DeletePortEvent@@YAKPEAPEAUPORT_EVENT@@@Z`
- size: `289`
- prototype: `unsigned int __fastcall(struct PORT_EVENT **)`
- caller_count: `21`
- callee_count: `4`
- tags: ``

## callers

- `0x180009454`
- `0x18000c444`
- `0x18000cfc0`
- `0x180019158`
- `0x1800193cc`
- `0x180027c70`
- `0x1800334c0`
- `0x1800345f4`
- `0x180036a5c`
- `0x180039210`
- `0x18003bd0c`
- `0x18003d95c`
- `0x18004145c`
- `0x180041c10`
- `0x180062dc4`
- `0x180064350`
- `0x180064780`
- `0x180064edc`
- `0x180065c18`
- `0x180066244`
- `0x180066d68`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000d4bc`
- `0x18000e620`

## import_xrefs

- `OneX!OneXFreeAuthParams` at `0x18000d5b2`
- `OneX!OneXFreeAuthParams` at `0x18000d5b2`

## pseudocode

```c
__int64 __fastcall DeletePortEvent(struct PORT_EVENT **a1)
{
  PVOID *v2; // rcx
  unsigned int v3; // esi
  struct PORT_EVENT *v4; // rdx
  unsigned int v5; // edi
  __int64 v7; // r8

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 17, &WPP_4b473b0d41083bd40dfc61d99b047aaf_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v3 = 0;
  if ( a1 )
  {
    v4 = *a1;
    if ( *a1 )
    {
      v5 = 0;
      if ( *((_DWORD *)v4 + 8) )
      {
        do
        {
          v7 = 16LL * v3;
          if ( *(_DWORD *)((char *)v4 + v7 + 40) == 4 || *(_DWORD *)((char *)v4 + v7 + 40) == 5 )
          {
            FreeMSMSecMemory((char *)v4 + v7 + 48);
          }
          else if ( *(_DWORD *)((char *)v4 + v7 + 40) == 6 )
          {
            OneXFreeAuthParams(*((_QWORD *)v4 + 2 * v3 + 6));
          }
          v4 = *a1;
          ++v3;
        }
        while ( v3 < *((_DWORD *)*a1 + 8) );
      }
      FreeMSMSecMemory(a1);
      goto LABEL_8;
    }
  }
  v5 = 87;
  if ( v2 == &WPP_GLOBAL_Control )
    return v5;
  if ( (*((_BYTE *)v2 + 68) & 1) != 0 )
  {
    WPP_SF_(v2[7], 18, &WPP_4b473b0d41083bd40dfc61d99b047aaf_Traceguids);
LABEL_8:
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_DWORD *)v2 + 17) & 0x100) != 0 )
    WPP_SF_d(v2[7], 19, &WPP_4b473b0d41083bd40dfc61d99b047aaf_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18000d4bc  push    rbx
0x18000d4be  push    rbp
0x18000d4bf  push    rsi
0x18000d4c0  push    rdi
0x18000d4c1  sub     rsp, 28h
0x18000d4c5  mov     rbx, rcx
0x18000d4c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4cf  lea     rbp, WPP_GLOBAL_Control
0x18000d4d6  cmp     rcx, rbp
0x18000d4d9  jz      short loc_18000D4E8
0x18000d4db  test    dword ptr [rcx+44h], 100h
0x18000d4e2  jnz     loc_18000D57C
0x18000d4e8  xor     esi, esi
0x18000d4ea  test    rbx, rbx
0x18000d4ed  jz      short loc_18000D52B
0x18000d4ef  mov     rdx, [rbx]
0x18000d4f2  test    rdx, rdx
0x18000d4f5  jz      short loc_18000D52B
0x18000d4f7  mov     edi, esi
0x18000d4f9  cmp     [rdx+20h], esi
0x18000d4fc  ja      short loc_18000D550
0x18000d4fe  mov     rcx, rbx
0x18000d501  call    FreeMSMSecMemory
0x18000d506  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d50d  cmp     rcx, rbp
0x18000d510  jz      short loc_18000D51F
0x18000d512  test    dword ptr [rcx+44h], 100h
0x18000d519  jnz     loc_18000D5C0
0x18000d51f  mov     eax, edi
0x18000d521  add     rsp, 28h
0x18000d525  pop     rdi
0x18000d526  pop     rsi
0x18000d527  pop     rbp
0x18000d528  pop     rbx
0x18000d529  retn
0x18000d52b  mov     edi, 57h ; 'W'
0x18000d530  cmp     rcx, rbp
0x18000d533  jz      short loc_18000D51F
0x18000d535  test    byte ptr [rcx+44h], 1
0x18000d539  jz      short loc_18000D50D
0x18000d53b  mov     rcx, [rcx+38h]
0x18000d53f  lea     edx, [rdi-45h]
0x18000d542  lea     r8, WPP_4b473b0d41083bd40dfc61d99b047aaf_Traceguids
0x18000d549  call    WPP_SF_
0x18000d54e  jmp     short loc_18000D506
0x18000d550  mov     r8d, esi
0x18000d553  shl     r8, 4
0x18000d557  mov     r9d, esi
0x18000d55a  mov     ecx, [r8+rdx+28h]
0x18000d55f  sub     ecx, 4
0x18000d562  jnz     short loc_18000D59D
0x18000d564  lea     rcx, [rdx+30h]
0x18000d568  add     rcx, r8
0x18000d56b  call    FreeMSMSecMemory
0x18000d570  mov     rdx, [rbx]
0x18000d573  inc     esi
0x18000d575  cmp     esi, [rdx+20h]
0x18000d578  jnb     short loc_18000D4FE
0x18000d57a  jmp     short loc_18000D550
0x18000d57c  mov     rcx, [rcx+38h]
0x18000d580  lea     r8, WPP_4b473b0d41083bd40dfc61d99b047aaf_Traceguids
0x18000d587  mov     edx, 11h
0x18000d58c  call    WPP_SF_
0x18000d591  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d598  jmp     loc_18000D4E8
0x18000d59d  sub     ecx, 1
0x18000d5a0  jz      short loc_18000D564
0x18000d5a2  cmp     ecx, 1
0x18000d5a5  jnz     short loc_18000D570
0x18000d5a7  lea     rcx, [r9+3]
0x18000d5ab  add     rcx, rcx
0x18000d5ae  mov     rcx, [rdx+rcx*8]
0x18000d5b2  call    cs:__imp_OneXFreeAuthParams
0x18000d5b9  nop     dword ptr [rax+rax+00h]
0x18000d5be  jmp     short loc_18000D570
0x18000d5c0  mov     rcx, [rcx+38h]
0x18000d5c4  lea     r8, WPP_4b473b0d41083bd40dfc61d99b047aaf_Traceguids
0x18000d5cb  mov     edx, 13h
0x18000d5d0  mov     r9d, edi
0x18000d5d3  call    WPP_SF_d
0x18000d5d8  jmp     loc_18000D51F
```
