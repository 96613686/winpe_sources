# McTemplateU0sqdz_EventWriteTransfer

- ea: `0x1800052f4`
- end: `0x1800053b8`
- name: `McTemplateU0sqdz_EventWriteTransfer`
- size: `196`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, int, char, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800046b0`

## callees

- `0x18000247c`
- `0x1800052f4`
- `0x1800180f0`

## pseudocode

```c
ULONG __fastcall McTemplateU0sqdz_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        char a5,
        const wchar_t *a6)
{
  const wchar_t *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-19h] BYREF
  const char *v11; // [rsp+40h] [rbp-9h]
  __int64 v12; // [rsp+48h] [rbp-1h]
  int *v13; // [rsp+50h] [rbp+7h]
  __int64 v14; // [rsp+58h] [rbp+Fh]
  char *v15; // [rsp+60h] [rbp+17h]
  __int64 v16; // [rsp+68h] [rbp+1Fh]
  const wchar_t *v17; // [rsp+70h] [rbp+27h]
  int v18; // [rsp+78h] [rbp+2Fh]
  int v19; // [rsp+7Ch] [rbp+33h]
  int v20; // [rsp+B8h] [rbp+6Fh] BYREF

  v20 = a4;
  v6 = a6;
  v11 = "CDiagnosticMetadataCollection::Add";
  v12 = 35;
  v13 = &v20;
  v15 = &a5;
  v14 = 4;
  v16 = 4;
  if ( a6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a6[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v8 = 10;
  }
  v18 = v8;
  v19 = 0;
  if ( !a6 )
    v6 = L"NULL";
  v17 = v6;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)v6,
           (const EVENT_DESCRIPTOR *)SDIAGPRV_EVENT_DEBUG_ADD_DIAGNOSTIC_METADATA_ERRORALREADYEXISTS,
           0,
           5u,
           &v10);
}

```

## disassembly

```asm
0x1800052f4  mov     [rsp-8+arg_18], r9d
0x1800052f9  push    rbp
0x1800052fa  lea     rbp, [rsp-47h]
0x1800052ff  sub     rsp, 90h
0x180005306  mov     rax, cs:__security_cookie
0x18000530d  xor     rax, rsp
0x180005310  mov     [rbp+47h+var_10], rax
0x180005314  mov     rcx, [rbp+47h+arg_28]
0x180005318  lea     rax, aCdiagnosticmet_8; "CDiagnosticMetadataCollection::Add"
0x18000531f  mov     [rbp+47h+var_50], rax
0x180005323  xor     r8d, r8d
0x180005326  mov     [rbp+47h+var_48], 23h ; '#'
0x18000532e  lea     rax, [rbp+47h+arg_18]
0x180005332  mov     [rbp+47h+var_40], rax
0x180005336  lea     rax, [rbp+47h+arg_20]
0x18000533a  mov     [rbp+47h+var_30], rax
0x18000533e  mov     [rbp+47h+var_38], 4
0x180005346  mov     [rbp+47h+var_28], 4
0x18000534e  test    rcx, rcx
0x180005351  jz      short loc_18000536A
0x180005353  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005357  inc     rax
0x18000535a  cmp     [rcx+rax*2], r8w
0x18000535f  jnz     short loc_180005357
0x180005361  lea     eax, ds:2[rax*2]
0x180005368  jmp     short loc_18000536F
0x18000536a  mov     eax, 0Ah
0x18000536f  test    rcx, rcx
0x180005372  mov     [rbp+47h+var_18], eax
0x180005375  lea     rdx, aNull_0; "NULL"
0x18000537c  mov     [rbp+47h+var_14], r8d
0x180005380  cmovz   rcx, rdx
0x180005384  lea     rax, [rbp+47h+var_60]
0x180005388  lea     rdx, SDIAGPRV_EVENT_DEBUG_ADD_DIAGNOSTIC_METADATA_ERRORALREADYEXISTS
0x18000538f  mov     [rbp+47h+var_20], rcx
0x180005393  mov     r9d, 5
0x180005399  mov     [rsp+90h+var_70], rax
0x18000539e  call    McGenEventWrite_EventWriteTransfer
0x1800053a3  mov     rcx, [rbp+47h+var_10]
0x1800053a7  xor     rcx, rsp; StackCookie
0x1800053aa  call    __security_check_cookie
0x1800053af  add     rsp, 90h
0x1800053b6  pop     rbp
0x1800053b7  retn
```
