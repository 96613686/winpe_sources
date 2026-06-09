# CreateOutInterfaceEntry

- ea: `0x18001cd94`
- end: `0x18001cf12`
- name: `CreateOutInterfaceEntry`
- size: `382`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18001c1a8`
- `0x18001c790`

## callees

- `0x18001cd94`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18001cdf6`
- `KERNEL32!HeapAlloc` at `0x18001cdf6`
- `rtutils!RouterLogEventA` at `0x18001ce78`
- `rtutils!RouterLogEventA` at `0x18001ce78`

## string_xrefs

- `0x18001ce18`: `CreateOutInterfaceEntry : Could not allocateout interface entry %x`

## pseudocode

```c
__int64 __fastcall CreateOutInterfaceEntry(__int64 a1, int a2, int a3, int a4, int a5, int a6, _QWORD *a7)
{
  _DWORD *v11; // rax
  _DWORD *v12; // rbx
  unsigned int v13; // edi
  __int16 v14; // ax
  _QWORD *v15; // rax
  int v17; // [rsp+30h] [rbp-848h] BYREF
  char v18[2044]; // [rsp+34h] [rbp-844h] BYREF

  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  *a7 = 0;
  v11 = HeapAlloc(hHeap, 0, 0x48u);
  v12 = v11;
  if ( v11 )
  {
    memset_0(v11, 0, 0x48u);
    v12[7] = a5;
    *((_WORD *)v12 + 16) = 1;
    v12[4] = a2;
    v12[5] = a3;
    v12[6] = a4;
    if ( a6 )
    {
      *((_WORD *)v12 + 18) = 1;
      v14 = 0x8000;
    }
    else
    {
      *((_WORD *)v12 + 19) = 1;
      v14 = 0x4000;
    }
    *((_WORD *)v12 + 17) |= v14;
    v15 = *(_QWORD **)(a1 + 8);
    if ( *v15 != a1 )
      __fastfail(3u);
    *(_QWORD *)v12 = a1;
    v13 = 0;
    *((_QWORD *)v12 + 1) = v15;
    *v15 = v12;
    *(_QWORD *)(a1 + 8) = v12;
    *a7 = v12;
  }
  else
  {
    v13 = 8;
    if ( qword_18002B8A8 )
    {
      LOWORD(v17) = 0;
      FormatRRASErrorString(&v17, L"CreateOutInterfaceEntry : Could not allocateout interface entry %x", 8);
      ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v17);
    }
    if ( dword_18002BA54 )
      RouterLogEventA(qword_18002BA58, 1u, 0xC353u, 0, 0, 8u);
  }
  return v13;
}

```

## disassembly

```asm
0x18001cd94  push    rbx
0x18001cd96  push    rbp
0x18001cd97  push    rsi
0x18001cd98  push    rdi
0x18001cd99  push    r14
0x18001cd9b  push    r15
0x18001cd9d  sub     rsp, 848h
0x18001cda4  mov     rax, cs:__security_cookie
0x18001cdab  xor     rax, rsp
0x18001cdae  mov     [rsp+878h+var_48], rax
0x18001cdb6  mov     r14, [rsp+878h+arg_30]
0x18001cdbe  mov     ebp, r8d
0x18001cdc1  mov     r15d, edx
0x18001cdc4  mov     rsi, rcx
0x18001cdc7  xor     eax, eax
0x18001cdc9  lea     rcx, [rsp+878h+var_844]; void *
0x18001cdce  xor     edx, edx; Val
0x18001cdd0  mov     [rsp+878h+var_848], eax
0x18001cdd4  mov     r8d, 7FCh; Size
0x18001cdda  mov     edi, r9d
0x18001cddd  call    memset_0
0x18001cde2  xor     edx, edx; dwFlags
0x18001cde4  mov     qword ptr [r14], 0
0x18001cdeb  mov     rcx, cs:hHeap; hHeap
0x18001cdf2  lea     r8d, [rdx+48h]; dwBytes
0x18001cdf6  call    cs:__imp_HeapAlloc
0x18001cdfc  mov     rbx, rax
0x18001cdff  test    rax, rax
0x18001ce02  jnz     short loc_18001CE80
0x18001ce04  cmp     cs:qword_18002B8A8, rax
0x18001ce0b  lea     edi, [rax+8]
0x18001ce0e  jz      short loc_18001CE48
0x18001ce10  mov     r8d, edi
0x18001ce13  mov     word ptr [rsp+878h+var_848], ax
0x18001ce18  lea     rdx, aCreateoutinter; "CreateOutInterfaceEntry : Could not all"...
0x18001ce1f  lea     rcx, [rsp+878h+var_848]
0x18001ce24  call    FormatRRASErrorString
0x18001ce29  mov     rdx, cs:qword_18002B8A8
0x18001ce30  lea     r8, [rsp+878h+var_848]
0x18001ce35  mov     rcx, cs:gMgmEtwContext
0x18001ce3c  mov     rax, cs:gMgmTemplateFunc
0x18001ce43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce48  mov     eax, 1
0x18001ce4d  cmp     cs:dword_18002BA54, eax
0x18001ce53  jb      loc_18001CEF0
0x18001ce59  mov     rcx, cs:qword_18002BA58; hLogHandle
0x18001ce60  xor     r9d, r9d; dwSubStringCount
0x18001ce63  mov     [rsp+878h+dwErrorCode], edi; dwErrorCode
0x18001ce67  mov     r8d, 0C353h; dwMessageId
0x18001ce6d  mov     edx, eax; dwEventType
0x18001ce6f  mov     [rsp+878h+plpszSubStringArray], 0; plpszSubStringArray
0x18001ce78  call    cs:__imp_RouterLogEventA
0x18001ce7e  jmp     short loc_18001CEF0
0x18001ce80  xor     edx, edx; Val
0x18001ce82  mov     rcx, rbx; void *
0x18001ce85  lea     r8d, [rdx+48h]; Size
0x18001ce89  call    memset_0
0x18001ce8e  cmp     [rsp+878h+arg_28], 0
0x18001ce96  mov     eax, [rsp+878h+arg_20]
0x18001ce9d  mov     [rbx+1Ch], eax
0x18001cea0  mov     eax, 1
0x18001cea5  mov     [rbx+20h], ax
0x18001cea9  mov     [rbx+10h], r15d
0x18001cead  mov     [rbx+14h], ebp
0x18001ceb0  mov     [rbx+18h], edi
0x18001ceb3  jz      short loc_18001CEC0
0x18001ceb5  mov     [rbx+24h], ax
0x18001ceb9  mov     eax, 8000h
0x18001cebe  jmp     short loc_18001CEC9
0x18001cec0  mov     [rbx+26h], ax
0x18001cec4  mov     eax, 4000h
0x18001cec9  or      [rbx+22h], ax
0x18001cecd  mov     rax, [rsi+8]
0x18001ced1  cmp     [rax], rsi
0x18001ced4  jz      short loc_18001CEDD
0x18001ced6  mov     ecx, 3
0x18001cedb  int     29h; Win8: RtlFailFast(ecx)
0x18001cedd  mov     [rbx], rsi
0x18001cee0  xor     edi, edi
0x18001cee2  mov     [rbx+8], rax
0x18001cee6  mov     [rax], rbx
0x18001cee9  mov     [rsi+8], rbx
0x18001ceed  mov     [r14], rbx
0x18001cef0  mov     eax, edi
0x18001cef2  mov     rcx, [rsp+878h+var_48]
0x18001cefa  xor     rcx, rsp; StackCookie
0x18001cefd  call    __security_check_cookie
0x18001cf02  add     rsp, 848h
0x18001cf09  pop     r15
0x18001cf0b  pop     r14
0x18001cf0d  pop     rdi
0x18001cf0e  pop     rsi
0x18001cf0f  pop     rbp
0x18001cf10  pop     rbx
0x18001cf11  retn
```
