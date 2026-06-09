# IsSaclAceInteresting(void *,uchar,int *)

- ea: `0x18002631c`
- end: `0x180026400`
- name: `?IsSaclAceInteresting@@YAJPEAXEPEAH@Z`
- size: `228`
- prototype: `__int64 __fastcall(void *, unsigned __int8, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024478`

## callees

- `0x18002631c`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800263cc`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800263cc`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800263be`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800263be`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002638f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002638f`

## string_xrefs

- `0x180026340`: `IsSaclAceInteresting`

## pseudocode

```c
__int64 __fastcall IsSaclAceInteresting(char *a1, char a2, int *a3)
{
  __int16 v6; // ax
  char *v7; // rdi
  __int64 v8; // rcx
  PUCHAR SidSubAuthorityCount; // rax
  unsigned int v10; // ebx
  int LastFailureAsHRESULT; // [rsp+20h] [rbp-48h] BYREF
  __int16 v13; // [rsp+24h] [rbp-44h]
  __int16 v14; // [rsp+26h] [rbp-42h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "IsSaclAceInteresting", 511, 1);
  v6 = 517;
  if ( !a1 )
  {
    LastFailureAsHRESULT = -2147024809;
LABEL_3:
    v14 = v6;
    goto LABEL_11;
  }
  LastFailureAsHRESULT = 0;
  v13 = 517;
  if ( a3 )
    *a3 = 0;
  if ( a2 == 17 )
  {
    v7 = a1 + 8;
    if ( !IsValidSid(v7) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8);
      v6 = 523;
      goto LABEL_3;
    }
    LastFailureAsHRESULT = 0;
    v13 = 523;
    SidSubAuthorityCount = GetSidSubAuthorityCount(v7);
    if ( *GetSidSubAuthority(v7, (unsigned int)*SidSubAuthorityCount - 1) < 0x3000 )
      *a3 = 1;
  }
LABEL_11:
  v10 = LastFailureAsHRESULT;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v10;
}

```

## disassembly

```asm
0x18002631c  mov     [rsp+arg_0], rbx
0x180026321  mov     [rsp+arg_8], rsi
0x180026326  push    rdi
0x180026327  sub     rsp, 60h
0x18002632b  mov     rbx, r8
0x18002632e  mov     sil, dl
0x180026331  mov     rdi, rcx
0x180026334  mov     r9d, 1; unsigned __int16
0x18002633a  mov     r8d, 1FFh; unsigned __int16
0x180026340  lea     rdx, aIssaclaceinter; "IsSaclAceInteresting"
0x180026347  lea     rcx, [rsp+68h+var_48]; this
0x18002634c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180026351  mov     eax, 205h
0x180026356  test    rdi, rdi
0x180026359  jnz     short loc_18002636A
0x18002635b  mov     [rsp+68h+var_48], 80070057h
0x180026363  mov     [rsp+68h+var_42], ax
0x180026368  jmp     short loc_1800263E0
0x18002636a  mov     [rsp+68h+var_48], 0
0x180026372  mov     [rsp+68h+var_44], ax
0x180026377  test    rbx, rbx
0x18002637a  jz      short loc_180026382
0x18002637c  mov     dword ptr [rbx], 0
0x180026382  cmp     sil, 11h
0x180026386  jnz     short loc_1800263E0
0x180026388  add     rdi, 8
0x18002638c  mov     rcx, rdi; pSid
0x18002638f  call    cs:__imp_IsValidSid
0x180026395  test    eax, eax
0x180026397  jnz     short loc_1800263A9
0x180026399  call    GetLastFailureAsHRESULT
0x18002639e  mov     [rsp+68h+var_48], eax
0x1800263a2  mov     eax, 20Bh
0x1800263a7  jmp     short loc_180026363
0x1800263a9  mov     [rsp+68h+var_48], 0
0x1800263b1  mov     eax, 20Bh
0x1800263b6  mov     [rsp+68h+var_44], ax
0x1800263bb  mov     rcx, rdi; pSid
0x1800263be  call    cs:__imp_GetSidSubAuthorityCount
0x1800263c4  movzx   edx, byte ptr [rax]
0x1800263c7  dec     edx; nSubAuthority
0x1800263c9  mov     rcx, rdi; pSid
0x1800263cc  call    cs:__imp_GetSidSubAuthority
0x1800263d2  cmp     dword ptr [rax], 3000h
0x1800263d8  jnb     short loc_1800263E0
0x1800263da  mov     dword ptr [rbx], 1
0x1800263e0  mov     ebx, [rsp+68h+var_48]
0x1800263e4  lea     rcx, [rsp+68h+var_48]; this
0x1800263e9  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800263ee  mov     eax, ebx
0x1800263f0  mov     rbx, [rsp+68h+arg_0]
0x1800263f5  mov     rsi, [rsp+68h+arg_8]
0x1800263fa  add     rsp, 60h
0x1800263fe  pop     rdi
0x1800263ff  retn
```
