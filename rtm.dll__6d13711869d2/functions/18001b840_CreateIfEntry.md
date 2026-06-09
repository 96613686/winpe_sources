# CreateIfEntry

- ea: `0x18001b840`
- end: `0x18001b9a6`
- name: `CreateIfEntry`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180014970`

## callees

- `0x18001b840`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18001b88e`
- `KERNEL32!HeapAlloc` at `0x18001b88e`
- `rtutils!RouterLogEventA` at `0x18001b90e`
- `rtutils!RouterLogEventA` at `0x18001b90e`

## string_xrefs

- `0x18001b8b0`: `CreateIfEntry : Failed to allocate entry %x`

## pseudocode

```c
__int64 __fastcall CreateIfEntry(__int64 a1, int a2, int a3, int a4, int a5)
{
  char *v9; // rax
  char *v10; // rcx
  unsigned int v11; // ebx
  __int16 v12; // ax
  _QWORD *v13; // rax
  int v15; // [rsp+30h] [rbp-838h] BYREF
  _BYTE v16[2044]; // [rsp+34h] [rbp-834h] BYREF

  v15 = 0;
  memset_0(v16, 0, sizeof(v16));
  v9 = (char *)HeapAlloc(hHeap, 0, 0x48u);
  v10 = v9;
  if ( v9 )
  {
    *(_DWORD *)(v9 + 34) = 0;
    *((_WORD *)v9 + 19) = 0;
    *((_DWORD *)v9 + 7) = a5;
    v12 = 0x8000;
    *((_DWORD *)v10 + 4) = a2;
    if ( a4 != 10 )
      v12 = 0x4000;
    *((_WORD *)v10 + 16) = v12;
    *((_DWORD *)v10 + 5) = a3;
    *((_DWORD *)v10 + 6) = a4;
    *((_QWORD *)v10 + 8) = v10 + 56;
    *((_QWORD *)v10 + 7) = v10 + 56;
    *((_QWORD *)v10 + 6) = v10 + 40;
    *((_QWORD *)v10 + 5) = v10 + 40;
    *((_QWORD *)v10 + 1) = v10;
    *(_QWORD *)v10 = v10;
    v13 = *(_QWORD **)(a1 + 8);
    if ( *v13 != a1 )
      __fastfail(3u);
    *(_QWORD *)v10 = a1;
    v11 = 0;
    *((_QWORD *)v10 + 1) = v13;
    *v13 = v10;
    *(_QWORD *)(a1 + 8) = v10;
  }
  else
  {
    v11 = 8;
    if ( qword_18002B8A8 )
    {
      LOWORD(v15) = 0;
      FormatRRASErrorString(&v15, L"CreateIfEntry : Failed to allocate entry %x", 8);
      ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v15);
    }
    if ( dword_18002BA54 )
      RouterLogEventA(qword_18002BA58, 1u, 0xC353u, 0, 0, 8u);
  }
  return v11;
}

```

## disassembly

```asm
0x18001b840  push    rbx
0x18001b842  push    rbp
0x18001b843  push    rsi
0x18001b844  push    rdi
0x18001b845  sub     rsp, 848h
0x18001b84c  mov     rax, cs:__security_cookie
0x18001b853  xor     rax, rsp
0x18001b856  mov     [rsp+868h+var_38], rax
0x18001b85e  mov     esi, r8d
0x18001b861  mov     ebp, edx
0x18001b863  mov     rdi, rcx
0x18001b866  xor     eax, eax
0x18001b868  xor     edx, edx; Val
0x18001b86a  mov     [rsp+868h+var_838], eax
0x18001b86e  mov     r8d, 7FCh; Size
0x18001b874  lea     rcx, [rsp+868h+var_834]; void *
0x18001b879  mov     ebx, r9d
0x18001b87c  call    memset_0
0x18001b881  mov     rcx, cs:hHeap; hHeap
0x18001b888  xor     edx, edx; dwFlags
0x18001b88a  lea     r8d, [rdx+48h]; dwBytes
0x18001b88e  call    cs:__imp_HeapAlloc
0x18001b894  mov     rcx, rax
0x18001b897  test    rax, rax
0x18001b89a  jnz     short loc_18001B916
0x18001b89c  cmp     cs:qword_18002B8A8, rax
0x18001b8a3  lea     ebx, [rax+8]
0x18001b8a6  jz      short loc_18001B8E0
0x18001b8a8  mov     r8d, ebx
0x18001b8ab  mov     word ptr [rsp+868h+var_838], ax
0x18001b8b0  lea     rdx, aCreateifentryF; "CreateIfEntry : Failed to allocate entr"...
0x18001b8b7  lea     rcx, [rsp+868h+var_838]
0x18001b8bc  call    FormatRRASErrorString
0x18001b8c1  mov     rdx, cs:qword_18002B8A8
0x18001b8c8  lea     r8, [rsp+868h+var_838]
0x18001b8cd  mov     rcx, cs:gMgmEtwContext
0x18001b8d4  mov     rax, cs:gMgmTemplateFunc
0x18001b8db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8e0  mov     edx, 1; dwEventType
0x18001b8e5  cmp     cs:dword_18002BA54, edx
0x18001b8eb  jb      loc_18001B988
0x18001b8f1  mov     rcx, cs:qword_18002BA58; hLogHandle
0x18001b8f8  xor     r9d, r9d; dwSubStringCount
0x18001b8fb  mov     [rsp+868h+dwErrorCode], ebx; dwErrorCode
0x18001b8ff  mov     r8d, 0C353h; dwMessageId
0x18001b905  mov     [rsp+868h+plpszSubStringArray], 0; plpszSubStringArray
0x18001b90e  call    cs:__imp_RouterLogEventA
0x18001b914  jmp     short loc_18001B988
0x18001b916  mov     dword ptr [rax+22h], 0
0x18001b91d  mov     edx, 4000h
0x18001b922  xor     eax, eax
0x18001b924  mov     [rcx+26h], ax
0x18001b928  cmp     ebx, 0Ah
0x18001b92b  mov     eax, [rsp+868h+arg_20]
0x18001b932  mov     [rcx+1Ch], eax
0x18001b935  mov     eax, 8000h
0x18001b93a  mov     [rcx+10h], ebp
0x18001b93d  cmovnz  ax, dx
0x18001b941  mov     [rcx+20h], ax
0x18001b945  lea     rax, [rcx+38h]
0x18001b949  mov     [rcx+14h], esi
0x18001b94c  mov     [rcx+18h], ebx
0x18001b94f  mov     [rax+8], rax
0x18001b953  mov     [rax], rax
0x18001b956  lea     rax, [rcx+28h]
0x18001b95a  mov     [rax+8], rax
0x18001b95e  mov     [rax], rax
0x18001b961  mov     [rcx+8], rcx
0x18001b965  mov     [rcx], rcx
0x18001b968  mov     rax, [rdi+8]
0x18001b96c  cmp     [rax], rdi
0x18001b96f  jz      short loc_18001B978
0x18001b971  mov     ecx, 3
0x18001b976  int     29h; Win8: RtlFailFast(ecx)
0x18001b978  mov     [rcx], rdi
0x18001b97b  xor     ebx, ebx
0x18001b97d  mov     [rcx+8], rax
0x18001b981  mov     [rax], rcx
0x18001b984  mov     [rdi+8], rcx
0x18001b988  mov     eax, ebx
0x18001b98a  mov     rcx, [rsp+868h+var_38]
0x18001b992  xor     rcx, rsp; StackCookie
0x18001b995  call    __security_check_cookie
0x18001b99a  add     rsp, 848h
0x18001b9a1  pop     rdi
0x18001b9a2  pop     rsi
0x18001b9a3  pop     rbp
0x18001b9a4  pop     rbx
0x18001b9a5  retn
```
