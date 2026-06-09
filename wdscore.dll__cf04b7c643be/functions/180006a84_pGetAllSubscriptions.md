# pGetAllSubscriptions

- ea: `0x180006a84`
- end: `0x180006c3b`
- name: `pGetAllSubscriptions`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180001f24`

## callees

- `0x180001ee8`
- `0x1800021c4`
- `0x180002250`
- `0x1800022bc`
- `0x180002344`
- `0x18000665c`
- `0x180006a84`
- `0x180006cb4`
- `0x18001dc70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ab0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ab0`

## string_xrefs

- `0x180006ac4`: `Could not allocate temporary subscription list (SEQ13)`

## pseudocode

```c
void *__fastcall pGetAllSubscriptions(__int64 a1, __int64 a2)
{
  void *v4; // rdi
  DWORD LastError; // ebx
  int *v6; // rax
  __int64 FirstSubscription; // rsi
  __int64 v9; // rbp
  __int64 NextListItem; // r14
  unsigned int v11; // r9d
  unsigned int v12; // r8d
  unsigned int v13; // edx
  unsigned int v14; // eax
  unsigned int v15; // ecx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  __int64 v19; // rbx
  __int64 v20; // rax
  LPCWSTR lpModuleName; // [rsp+88h] [rbp+0h]

  v4 = (void *)ConstructList(pDestructSubscription, pSerializeSubscription);
  if ( v4 )
  {
    FirstSubscription = pGetFirstSubscription(a1, 0, 0);
    v9 = pGetFirstSubscription(a1, *(unsigned int *)(a2 + 40), 0);
    NextListItem = pGetFirstSubscription(a1, *(unsigned int *)(a2 + 40), *(unsigned int *)(a2 + 44));
    while ( 1 )
    {
      if ( FirstSubscription )
        v11 = *(_DWORD *)(*(_QWORD *)(FirstSubscription + 40) + 40LL);
      else
        v11 = -1;
      if ( v9 )
        v12 = *(_DWORD *)(*(_QWORD *)(v9 + 40) + 40LL);
      else
        v12 = -1;
      if ( NextListItem )
        v13 = *(_DWORD *)(*(_QWORD *)(NextListItem + 40) + 40LL);
      else
        v13 = -1;
      v14 = v12;
      v15 = v13;
      if ( v12 >= v11 )
        v14 = v11;
      if ( v13 >= v14 )
        v15 = v14;
      v16 = v15 == v11;
      if ( v15 == v12 )
        v16 = 2;
      if ( v15 == v13 )
        goto LABEL_24;
      v17 = v16 - 1;
      if ( v17 )
      {
        v18 = v17 - 1;
        if ( v18 )
        {
          if ( v18 != 1 )
            return v4;
LABEL_24:
          v19 = NextListItem;
          NextListItem = GetNextListItem(NextListItem);
          goto LABEL_25;
        }
        v19 = v9;
        v9 = GetNextListItem(v9);
      }
      else
      {
        v19 = FirstSubscription;
        FirstSubscription = GetNextListItem(FirstSubscription);
      }
LABEL_25:
      if ( !v19 )
        return v4;
      v20 = pCopySubscription(v19);
      if ( !v20 )
      {
        DestructList(v4);
        return 0;
      }
      AddToTail(v4, v20);
    }
  }
  LastError = GetLastError();
  v6 = (int *)ConstructPartialMsgW(0x20000A1u, "Could not allocate temporary subscription list (SEQ13)");
  WdsSetupLogMessageW(
    v6,
    589824,
    (__int64)L"D",
    0,
    0xE6Fu,
    L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
    L"pGetAllSubscriptions",
    lpModuleName,
    LastError,
    0,
    0);
  return 0;
}

```

## disassembly

```asm
0x180006a84  push    rbx
0x180006a86  push    rbp
0x180006a87  push    rsi
0x180006a88  push    rdi
0x180006a89  push    r14
0x180006a8b  sub     rsp, 60h
0x180006a8f  mov     rbx, rdx
0x180006a92  mov     r14, rcx
0x180006a95  lea     rdx, pSerializeSubscription
0x180006a9c  lea     rcx, pDestructSubscription
0x180006aa3  call    ConstructList
0x180006aa8  mov     rdi, rax
0x180006aab  test    rax, rax
0x180006aae  jnz     short loc_180006B2F
0x180006ab0  call    cs:__imp_GetLastError
0x180006ab7  nop     dword ptr [rax+rax+00h]
0x180006abc  mov     rdi, [rsp+88h]
0x180006ac4  lea     rdx, aCouldNotAlloca_4; "Could not allocate temporary subscripti"...
0x180006acb  mov     ecx, 20000A1h; unsigned int
0x180006ad0  mov     ebx, eax
0x180006ad2  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180006ad7  mov     [rsp+88h+var_38], 0; int
0x180006adf  lea     r8, aD_1; "D"
0x180006ae6  mov     [rsp+88h+var_40], 0; __int64
0x180006aef  mov     rcx, rax; int
0x180006af2  mov     [rsp+88h+var_48], ebx; int
0x180006af6  lea     rax, aPgetallsubscri; "pGetAllSubscriptions"
0x180006afd  mov     [rsp+88h+lpModuleName], rdi; lpModuleName
0x180006b02  xor     r9d, r9d; int
0x180006b05  mov     [rsp+88h+var_58], rax; __int64
0x180006b0a  mov     edx, 90000h; int
0x180006b0f  lea     rax, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\panther\\engine"...
0x180006b16  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x180006b1b  mov     [rsp+88h+var_68], 0E6Fh; int
0x180006b23  call    WdsSetupLogMessageW
0x180006b28  xor     eax, eax
0x180006b2a  jmp     loc_180006C2F
0x180006b2f  xor     r8d, r8d
0x180006b32  xor     edx, edx
0x180006b34  mov     rcx, r14
0x180006b37  call    pGetFirstSubscription
0x180006b3c  mov     edx, [rbx+28h]
0x180006b3f  xor     r8d, r8d
0x180006b42  mov     rcx, r14
0x180006b45  mov     rsi, rax
0x180006b48  call    pGetFirstSubscription
0x180006b4d  mov     r8d, [rbx+2Ch]
0x180006b51  mov     rcx, r14
0x180006b54  mov     edx, [rbx+28h]
0x180006b57  mov     rbp, rax
0x180006b5a  call    pGetFirstSubscription
0x180006b5f  mov     r14, rax
0x180006b62  test    rsi, rsi
0x180006b65  jz      short loc_180006B71
0x180006b67  mov     rcx, [rsi+28h]
0x180006b6b  mov     r9d, [rcx+28h]
0x180006b6f  jmp     short loc_180006B75
0x180006b71  or      r9d, 0FFFFFFFFh
0x180006b75  test    rbp, rbp
0x180006b78  jz      short loc_180006B84
0x180006b7a  mov     rax, [rbp+28h]
0x180006b7e  mov     r8d, [rax+28h]
0x180006b82  jmp     short loc_180006B88
0x180006b84  or      r8d, 0FFFFFFFFh
0x180006b88  test    r14, r14
0x180006b8b  jz      short loc_180006B96
0x180006b8d  mov     rax, [r14+28h]
0x180006b91  mov     edx, [rax+28h]
0x180006b94  jmp     short loc_180006B99
0x180006b96  or      edx, 0FFFFFFFFh
0x180006b99  cmp     r8d, r9d
0x180006b9c  mov     eax, r8d
0x180006b9f  mov     ecx, edx
0x180006ba1  cmovnb  eax, r9d
0x180006ba5  cmp     edx, eax
0x180006ba7  cmovnb  ecx, eax
0x180006baa  xor     eax, eax
0x180006bac  cmp     ecx, r9d
0x180006baf  mov     r9d, 2
0x180006bb5  setz    al
0x180006bb8  cmp     ecx, r8d
0x180006bbb  cmovz   eax, r9d
0x180006bbf  cmp     ecx, edx
0x180006bc1  jz      short loc_180006BD2
0x180006bc3  sub     eax, 1
0x180006bc6  jz      short loc_180006C12
0x180006bc8  sub     eax, 1
0x180006bcb  jz      short loc_180006C02
0x180006bcd  cmp     eax, 1
0x180006bd0  jnz     short loc_180006C2C
0x180006bd2  mov     rcx, r14
0x180006bd5  mov     rbx, r14
0x180006bd8  call    GetNextListItem
0x180006bdd  mov     r14, rax
0x180006be0  test    rbx, rbx
0x180006be3  jz      short loc_180006C2C
0x180006be5  mov     rcx, rbx
0x180006be8  call    pCopySubscription
0x180006bed  mov     rcx, rdi; lpMem
0x180006bf0  test    rax, rax
0x180006bf3  jz      short loc_180006C22
0x180006bf5  mov     rdx, rax
0x180006bf8  call    AddToTail
0x180006bfd  jmp     loc_180006B62
0x180006c02  mov     rcx, rbp
0x180006c05  mov     rbx, rbp
0x180006c08  call    GetNextListItem
0x180006c0d  mov     rbp, rax
0x180006c10  jmp     short loc_180006BE0
0x180006c12  mov     rcx, rsi
0x180006c15  mov     rbx, rsi
0x180006c18  call    GetNextListItem
0x180006c1d  mov     rsi, rax
0x180006c20  jmp     short loc_180006BE0
0x180006c22  call    DestructList
0x180006c27  jmp     loc_180006B28
0x180006c2c  mov     rax, rdi
0x180006c2f  add     rsp, 60h
0x180006c33  pop     r14
0x180006c35  pop     rdi
0x180006c36  pop     rsi
0x180006c37  pop     rbp
0x180006c38  pop     rbx
0x180006c39  retn
```
