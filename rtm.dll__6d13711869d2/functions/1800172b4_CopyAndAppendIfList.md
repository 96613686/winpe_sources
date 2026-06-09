# CopyAndAppendIfList

- ea: `0x1800172b4`
- end: `0x180017404`
- name: `CopyAndAppendIfList`
- size: `336`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001740c`

## callees

- `0x1800172b4`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180017308`
- `KERNEL32!HeapAlloc` at `0x180017308`
- `rtutils!RouterLogEventA` at `0x1800173d9`
- `rtutils!RouterLogEventA` at `0x1800173d9`

## string_xrefs

- `0x180017377`: `CopyAndAppendIfList : Could not allocateout interface entry %x`

## pseudocode

```c
void __fastcall CopyAndAppendIfList(__int64 a1, __int64 *a2, __int64 *a3)
{
  _OWORD *v6; // rax
  _QWORD *v7; // rcx
  int v8; // [rsp+30h] [rbp-818h] BYREF
  _BYTE v9[2044]; // [rsp+34h] [rbp-814h] BYREF

  v8 = 0;
  memset_0(v9, 0, sizeof(v9));
  while ( a2 != a3 )
  {
    v6 = HeapAlloc(hHeap, 0, 0x48u);
    if ( !v6 )
    {
      if ( qword_18002B8A8 )
      {
        LOWORD(v8) = 0;
        FormatRRASErrorString(&v8, L"CopyAndAppendIfList : Could not allocateout interface entry %x", 8);
        ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v8);
      }
      if ( dword_18002BA54 )
        RouterLogEventA(qword_18002BA58, 1u, 0xC353u, 0, 0, 8u);
      return;
    }
    *v6 = *(_OWORD *)a2;
    v6[1] = *((_OWORD *)a2 + 1);
    v6[2] = *((_OWORD *)a2 + 2);
    v6[3] = *((_OWORD *)a2 + 3);
    *((_QWORD *)v6 + 8) = a2[8];
    v7 = *(_QWORD **)(a1 + 8);
    if ( *v7 != a1 )
      __fastfail(3u);
    *(_QWORD *)v6 = a1;
    *((_QWORD *)v6 + 1) = v7;
    *v7 = v6;
    *(_QWORD *)(a1 + 8) = v6;
    a2 = (__int64 *)*a2;
  }
}

```

## disassembly

```asm
0x1800172b4  mov     [rsp+arg_8], rbx
0x1800172b9  mov     [rsp+arg_10], rsi
0x1800172be  push    rdi
0x1800172bf  sub     rsp, 840h
0x1800172c6  mov     rax, cs:__security_cookie
0x1800172cd  xor     rax, rsp
0x1800172d0  mov     [rsp+848h+var_18], rax
0x1800172d8  mov     rsi, r8
0x1800172db  mov     rbx, rdx
0x1800172de  mov     rdi, rcx
0x1800172e1  xor     eax, eax
0x1800172e3  xor     edx, edx; Val
0x1800172e5  mov     [rsp+848h+var_818], eax
0x1800172e9  mov     r8d, 7FCh; Size
0x1800172ef  lea     rcx, [rsp+848h+var_814]; void *
0x1800172f4  call    memset_0
0x1800172f9  jmp     short loc_180017355
0x1800172fb  mov     rcx, cs:hHeap; hHeap
0x180017302  xor     edx, edx; dwFlags
0x180017304  lea     r8d, [rdx+48h]; dwBytes
0x180017308  call    cs:__imp_HeapAlloc
0x18001730e  test    rax, rax
0x180017311  jz      short loc_180017366
0x180017313  movups  xmm0, xmmword ptr [rbx]
0x180017316  movups  xmmword ptr [rax], xmm0
0x180017319  movups  xmm1, xmmword ptr [rbx+10h]
0x18001731d  movups  xmmword ptr [rax+10h], xmm1
0x180017321  movups  xmm0, xmmword ptr [rbx+20h]
0x180017325  movups  xmmword ptr [rax+20h], xmm0
0x180017329  movups  xmm1, xmmword ptr [rbx+30h]
0x18001732d  movups  xmmword ptr [rax+30h], xmm1
0x180017331  movsd   xmm0, qword ptr [rbx+40h]
0x180017336  movsd   qword ptr [rax+40h], xmm0
0x18001733b  mov     rcx, [rdi+8]
0x18001733f  cmp     [rcx], rdi
0x180017342  jnz     short loc_18001735F
0x180017344  mov     [rax], rdi
0x180017347  mov     [rax+8], rcx
0x18001734b  mov     [rcx], rax
0x18001734e  mov     [rdi+8], rax
0x180017352  mov     rbx, [rbx]
0x180017355  cmp     rbx, rsi
0x180017358  jnz     short loc_1800172FB
0x18001735a  jmp     loc_1800173DF
0x18001735f  mov     ecx, 3
0x180017364  int     29h; Win8: RtlFailFast(ecx)
0x180017366  cmp     cs:qword_18002B8A8, 0
0x18001736e  mov     ebx, 8
0x180017373  jz      short loc_1800173AF
0x180017375  xor     eax, eax
0x180017377  lea     rdx, aCopyandappendi; "CopyAndAppendIfList : Could not allocat"...
0x18001737e  mov     r8d, ebx
0x180017381  mov     word ptr [rsp+848h+var_818], ax
0x180017386  lea     rcx, [rsp+848h+var_818]
0x18001738b  call    FormatRRASErrorString
0x180017390  mov     rdx, cs:qword_18002B8A8
0x180017397  lea     r8, [rsp+848h+var_818]
0x18001739c  mov     rcx, cs:gMgmEtwContext
0x1800173a3  mov     rax, cs:gMgmTemplateFunc
0x1800173aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173af  mov     edx, 1; dwEventType
0x1800173b4  cmp     cs:dword_18002BA54, edx
0x1800173ba  jb      short loc_1800173DF
0x1800173bc  mov     rcx, cs:qword_18002BA58; hLogHandle
0x1800173c3  xor     r9d, r9d; dwSubStringCount
0x1800173c6  mov     [rsp+848h+dwErrorCode], ebx; dwErrorCode
0x1800173ca  mov     r8d, 0C353h; dwMessageId
0x1800173d0  mov     [rsp+848h+plpszSubStringArray], 0; plpszSubStringArray
0x1800173d9  call    cs:__imp_RouterLogEventA
0x1800173df  mov     rcx, [rsp+848h+var_18]
0x1800173e7  xor     rcx, rsp; StackCookie
0x1800173ea  call    __security_check_cookie
0x1800173ef  lea     r11, [rsp+848h+var_8]
0x1800173f7  mov     rbx, [r11+18h]
0x1800173fb  mov     rsi, [r11+20h]
0x1800173ff  mov     rsp, r11
0x180017402  pop     rdi
0x180017403  retn
```
