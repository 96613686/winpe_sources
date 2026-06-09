# UnScopeIfAndInvokeCallbacks

- ea: `0x18001ad04`
- end: `0x18001af0e`
- name: `UnScopeIfAndInvokeCallbacks`
- size: `522`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001a360`

## callees

- `0x18001928c`
- `0x18001ad04`
- `0x18001b548`
- `0x18001dcbc`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001ae23`
- `KERNEL32!HeapFree` at `0x18001ae23`

## string_xrefs

- `0x18001aea1`: `Owning protocol(%d, %d) for interface(%d, %d) not found`

## pseudocode

```c
int __fastcall UnScopeIfAndInvokeCallbacks(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 *v6; // rcx
  __int64 **v7; // rax
  unsigned int v8; // r8d
  __int64 ProtocolEntry; // rax
  __int64 **v10; // rcx
  bool v11; // zf
  unsigned int v12; // edx
  unsigned int v13; // r8d
  __int64 v15; // [rsp+20h] [rbp-E0h]
  __int64 v16; // [rsp+28h] [rbp-D8h]
  int v17; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+48h] [rbp-B8h] BYREF
  int v19; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v20[2044]; // [rsp+54h] [rbp-ACh] BYREF

  v17 = 0;
  v18 = 0;
  v19 = 0;
  memset_0(v20, 0, sizeof(v20));
  v6 = (__int64 *)*a3;
  if ( a3 != (__int64 *)*a3 )
  {
    if ( (__int64 *)v6[1] != a3 )
      goto LABEL_12;
    v7 = (__int64 **)a3[1];
    if ( *v7 != a3 )
      goto LABEL_12;
    *v7 = v6;
    v6[1] = (__int64)v7;
    *a3 = (__int64)a3;
    a3[1] = (__int64)a3;
  }
  if ( (unsigned int)FindOutInterfaceEntry(
                       (int)a2 + 48,
                       *((_DWORD *)a3 + 4),
                       *((_DWORD *)a3 + 5),
                       *((_DWORD *)a3 + 6),
                       *((_DWORD *)a3 + 7),
                       (__int64)&v17,
                       (__int64)&v18) )
  {
    if ( qword_18002B8A8 )
    {
      LOWORD(v19) = 0;
      LODWORD(v16) = *(_DWORD *)(a1 + 32);
      LODWORD(v15) = *(_DWORD *)(a2 + 104);
      FormatRRASErrorString(
        &v19,
        L"Interface (%d-%d) present in OIF list of (%x-%x) inspite of being scoped",
        *((unsigned int *)a3 + 4),
        v8,
        v15,
        v16);
      ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v19);
    }
    LODWORD(ProtocolEntry) = HeapFree(hHeap, 0, a3);
    return ProtocolEntry;
  }
  ProtocolEntry = v18;
  if ( !v18 )
    ProtocolEntry = a2 + 48;
  v10 = *(__int64 ***)(ProtocolEntry + 8);
  if ( *v10 != (__int64 *)ProtocolEntry )
LABEL_12:
    __fastfail(3u);
  v11 = v17 == 0;
  *a3 = ProtocolEntry;
  a3[1] = (__int64)v10;
  *v10 = a3;
  *(_QWORD *)(ProtocolEntry + 8) = a3;
  if ( !v11 )
  {
    ++*(_DWORD *)(a2 + 40);
    ProtocolEntry = GetProtocolEntry(&qword_18002B9A8, *((unsigned int *)a3 + 6), *((unsigned int *)a3 + 7));
    if ( ProtocolEntry )
    {
      LODWORD(ProtocolEntry) = InvokeJoinAlertCallbacks(a1, a2, a3, *((_WORD *)a3 + 17) & 0x8000, ProtocolEntry);
    }
    else if ( qword_18002B8A8 )
    {
      LOWORD(v19) = 0;
      LODWORD(v16) = *((_DWORD *)a3 + 5);
      LODWORD(v15) = *((_DWORD *)a3 + 4);
      FormatRRASErrorString(&v19, L"Owning protocol(%d, %d) for interface(%d, %d) not found", v12, v13, v15, v16);
      LODWORD(ProtocolEntry) = ((__int64 (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(
                                 gMgmEtwContext,
                                 qword_18002B8A8,
                                 &v19);
    }
  }
  return ProtocolEntry;
}

```

## disassembly

```asm
0x18001ad04  push    rbp
0x18001ad06  push    rbx
0x18001ad07  push    rsi
0x18001ad08  push    rdi
0x18001ad09  push    r14
0x18001ad0b  lea     rbp, [rsp-760h]
0x18001ad13  sub     rsp, 860h
0x18001ad1a  mov     rax, cs:__security_cookie
0x18001ad21  xor     rax, rsp
0x18001ad24  mov     [rbp+780h+var_30], rax
0x18001ad2b  mov     rbx, r8
0x18001ad2e  mov     [rsp+880h+var_840], 0
0x18001ad36  mov     rdi, rdx
0x18001ad39  mov     [rsp+880h+var_838], 0
0x18001ad42  mov     r14, rcx
0x18001ad45  xor     eax, eax
0x18001ad47  xor     edx, edx; Val
0x18001ad49  mov     [rsp+880h+var_830], eax
0x18001ad4d  mov     r8d, 7FCh; Size
0x18001ad53  lea     rcx, [rsp+880h+var_82C]; void *
0x18001ad58  call    memset_0
0x18001ad5d  mov     rcx, [rbx]
0x18001ad60  cmp     rbx, rcx
0x18001ad63  jz      short loc_18001AD8A
0x18001ad65  cmp     [rcx+8], rbx
0x18001ad69  jnz     loc_18001AE43
0x18001ad6f  mov     rax, [rbx+8]
0x18001ad73  cmp     [rax], rbx
0x18001ad76  jnz     loc_18001AE43
0x18001ad7c  mov     [rax], rcx
0x18001ad7f  mov     [rcx+8], rax
0x18001ad83  mov     [rbx], rbx
0x18001ad86  mov     [rbx+8], rbx
0x18001ad8a  mov     r9d, [rbx+18h]
0x18001ad8e  lea     rax, [rsp+880h+var_838]
0x18001ad93  mov     edx, [rbx+10h]
0x18001ad96  lea     rsi, [rdi+30h]
0x18001ad9a  mov     r8d, [rbx+14h]
0x18001ad9e  mov     rcx, rsi
0x18001ada1  mov     [rsp+880h+var_850], rax
0x18001ada6  lea     rax, [rsp+880h+var_840]
0x18001adab  mov     [rsp+880h+var_858], rax
0x18001adb0  mov     eax, [rbx+1Ch]
0x18001adb3  mov     dword ptr [rsp+880h+var_860], eax
0x18001adb7  call    FindOutInterfaceEntry
0x18001adbc  test    eax, eax
0x18001adbe  jz      short loc_18001AE2E
0x18001adc0  cmp     cs:qword_18002B8A8, 0
0x18001adc8  jz      short loc_18001AE17
0x18001adca  xor     eax, eax
0x18001adcc  lea     rdx, aInterfaceDDPre; "Interface (%d-%d) present in OIF list o"...
0x18001add3  mov     word ptr [rsp+880h+var_830], ax
0x18001add8  lea     rcx, [rsp+880h+var_830]
0x18001addd  mov     eax, [r14+20h]
0x18001ade1  mov     r9d, r8d
0x18001ade4  mov     r8d, [rbx+10h]
0x18001ade8  mov     dword ptr [rsp+880h+var_858], eax
0x18001adec  mov     eax, [rdi+68h]
0x18001adef  mov     dword ptr [rsp+880h+var_860], eax
0x18001adf3  call    FormatRRASErrorString
0x18001adf8  mov     rdx, cs:qword_18002B8A8
0x18001adff  lea     r8, [rsp+880h+var_830]
0x18001ae04  mov     rcx, cs:gMgmEtwContext
0x18001ae0b  mov     rax, cs:gMgmTemplateFunc
0x18001ae12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae17  mov     rcx, cs:hHeap; hHeap
0x18001ae1e  mov     r8, rbx; lpMem
0x18001ae21  xor     edx, edx; dwFlags
0x18001ae23  call    cs:__imp_HeapFree
0x18001ae29  jmp     loc_18001AEF1
0x18001ae2e  mov     rax, [rsp+880h+var_838]
0x18001ae33  test    rax, rax
0x18001ae36  cmovz   rax, rsi
0x18001ae3a  mov     rcx, [rax+8]
0x18001ae3e  cmp     [rcx], rax
0x18001ae41  jz      short loc_18001AE4A
0x18001ae43  mov     ecx, 3
0x18001ae48  int     29h; Win8: RtlFailFast(ecx)
0x18001ae4a  cmp     [rsp+880h+var_840], 0
0x18001ae4f  mov     [rbx], rax
0x18001ae52  mov     [rbx+8], rcx
0x18001ae56  mov     [rcx], rbx
0x18001ae59  mov     [rax+8], rbx
0x18001ae5d  jz      loc_18001AEF1
0x18001ae63  inc     dword ptr [rdi+28h]
0x18001ae66  lea     rcx, qword_18002B9A8
0x18001ae6d  mov     r8d, [rbx+1Ch]
0x18001ae71  mov     edx, [rbx+18h]
0x18001ae74  call    GetProtocolEntry
0x18001ae79  test    rax, rax
0x18001ae7c  jnz     short loc_18001AED2
0x18001ae7e  cmp     cs:qword_18002B8A8, rax
0x18001ae85  jz      short loc_18001AEF1
0x18001ae87  mov     word ptr [rsp+880h+var_830], ax
0x18001ae8c  lea     rcx, [rsp+880h+var_830]
0x18001ae91  mov     eax, [rbx+14h]
0x18001ae94  mov     r9d, r8d
0x18001ae97  mov     dword ptr [rsp+880h+var_858], eax
0x18001ae9b  mov     r8d, edx
0x18001ae9e  mov     eax, [rbx+10h]
0x18001aea1  lea     rdx, aOwningProtocol; "Owning protocol(%d, %d) for interface(%"...
0x18001aea8  mov     dword ptr [rsp+880h+var_860], eax
0x18001aeac  call    FormatRRASErrorString
0x18001aeb1  mov     rdx, cs:qword_18002B8A8
0x18001aeb8  lea     r8, [rsp+880h+var_830]
0x18001aebd  mov     rcx, cs:gMgmEtwContext
0x18001aec4  mov     rax, cs:gMgmTemplateFunc
0x18001aecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aed0  jmp     short loc_18001AEF1
0x18001aed2  movzx   r9d, word ptr [rbx+22h]
0x18001aed7  mov     r8, rbx
0x18001aeda  and     r9d, 8000h
0x18001aee1  mov     [rsp+880h+var_860], rax
0x18001aee6  mov     rdx, rdi
0x18001aee9  mov     rcx, r14
0x18001aeec  call    InvokeJoinAlertCallbacks
0x18001aef1  mov     rcx, [rbp+780h+var_30]
0x18001aef8  xor     rcx, rsp; StackCookie
0x18001aefb  call    __security_check_cookie
0x18001af00  add     rsp, 860h
0x18001af07  pop     r14
0x18001af09  pop     rdi
0x18001af0a  pop     rsi
0x18001af0b  pop     rbx
0x18001af0c  pop     rbp
0x18001af0d  retn
```
