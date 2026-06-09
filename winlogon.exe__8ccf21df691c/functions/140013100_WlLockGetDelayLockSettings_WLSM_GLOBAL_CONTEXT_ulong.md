# WlLockGetDelayLockSettings(_WLSM_GLOBAL_CONTEXT *,ulong *)

- ea: `0x140013100`
- end: `0x1400132d9`
- name: `?WlLockGetDelayLockSettings@@YAXPEAU_WLSM_GLOBAL_CONTEXT@@PEAK@Z`
- size: `473`
- prototype: `void __fastcall(struct _WLSM_GLOBAL_CONTEXT *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140013c40`

## callees

- `0x1400057f4`
- `0x140013100`
- `0x140053720`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140013178`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400131ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140013178`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400131ff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400131b2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400131b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400131c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400132a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009d688`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400131c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400132a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009d688`

## pseudocode

```c
void __fastcall WlLockGetDelayLockSettings(struct _WLSM_GLOBAL_CONTEXT *a1, unsigned int *a2)
{
  int v3; // r14d
  unsigned int v4; // ebx
  __int64 v5; // rax
  HKEY v6; // rcx
  CUser *v7; // r10
  unsigned int v8; // eax
  DWORD cbData; // [rsp+30h] [rbp-258h] BYREF
  DWORD Type; // [rsp+34h] [rbp-254h] BYREF
  int v11; // [rsp+38h] [rbp-250h]
  HKEY phkResult; // [rsp+40h] [rbp-248h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-240h] BYREF
  BYTE Data[528]; // [rsp+50h] [rbp-238h] BYREF

  phkResult = 0;
  hKey = 0;
  v3 = 0;
  v11 = 0;
  v4 = -1;
  Type = 0;
  cbData = 0;
  v5 = *((_QWORD *)a1 + 4);
  if ( v5 )
  {
    v6 = *(HKEY *)(v5 + 232);
    phkResult = v6;
    goto LABEL_3;
  }
  v8 = RegOpenKeyExW(HKEY_USERS, L".DEFAULT", 0, 0x20019u, &phkResult);
  if ( !v8 )
  {
    v3 = 1;
    v11 = 1;
    v6 = phkResult;
LABEL_3:
    if ( !RegOpenKeyExW(v6, L"Control Panel\\Desktop", 0, 0x20019u, &hKey) )
    {
      cbData = 520;
      if ( !RegQueryValueExW(hKey, L"DelayLockInterval", 0, &Type, Data, &cbData) && Type == 4 )
        v4 = *(_DWORD *)Data;
      RegCloseKey(hKey);
    }
    goto LABEL_6;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids, v8);
LABEL_6:
    v7 = WPP_GLOBAL_Control;
  }
  if ( phkResult && v3 )
  {
    RegCloseKey(phkResult);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != (CUser *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 4u )
    WPP_SF_d(*((_QWORD *)v7 + 2), 12, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids, v4);
  *a2 = v4;
}

```

## disassembly

```asm
0x140013100  mov     [rsp+arg_10], rbx
0x140013105  push    rsi
0x140013106  push    rdi
0x140013107  push    r14
0x140013109  sub     rsp, 270h
0x140013110  mov     rax, cs:__security_cookie
0x140013117  xor     rax, rsp
0x14001311a  mov     [rsp+288h+var_28], rax
0x140013122  mov     rdi, rdx
0x140013125  xor     eax, eax
0x140013127  mov     [rsp+288h+var_248], rax
0x14001312c  mov     [rsp+288h+hKey], rax
0x140013131  mov     r14d, eax
0x140013134  mov     [rsp+288h+var_250], eax
0x140013138  mov     ebx, 0FFFFFFFFh
0x14001313d  mov     [rsp+288h+Type], eax
0x140013141  mov     [rsp+288h+cbData], eax
0x140013145  mov     rax, [rcx+20h]
0x140013149  test    rax, rax
0x14001314c  jz      loc_1400131DE
0x140013152  mov     rcx, [rax+0E8h]; hKey
0x140013159  mov     [rsp+288h+var_248], rcx
0x14001315e  lea     rax, [rsp+288h+hKey]
0x140013163  mov     [rsp+288h+phkResult], rax; phkResult
0x140013168  mov     r9d, 20019h; samDesired
0x14001316e  xor     r8d, r8d; ulOptions
0x140013171  lea     rdx, aControlPanelDe; "Control Panel\\Desktop"
0x140013178  call    cs:__imp_RegOpenKeyExW
0x14001317e  test    eax, eax
0x140013180  jnz     short loc_1400131CB
0x140013182  mov     [rsp+288h+cbData], 208h
0x14001318a  lea     rax, [rsp+288h+cbData]
0x14001318f  mov     [rsp+288h+lpcbData], rax; lpcbData
0x140013194  lea     rax, [rsp+288h+Data]
0x140013199  mov     [rsp+288h+phkResult], rax; lpData
0x14001319e  lea     r9, [rsp+288h+Type]; lpType
0x1400131a3  xor     r8d, r8d; lpReserved
0x1400131a6  lea     rdx, aDelaylockinter; "DelayLockInterval"
0x1400131ad  mov     rcx, [rsp+288h+hKey]; hKey
0x1400131b2  call    cs:__imp_RegQueryValueExW
0x1400131b8  test    eax, eax
0x1400131ba  jz      loc_140013259
0x1400131c0  mov     rcx, [rsp+288h+hKey]; hKey
0x1400131c5  call    cs:__imp_RegCloseKey
0x1400131cb  lea     rsi, WPP_GLOBAL_Control
0x1400131d2  mov     r10, cs:WPP_GLOBAL_Control
0x1400131d9  jmp     loc_140013268
0x1400131de  lea     rax, [rsp+288h+var_248]
0x1400131e3  mov     [rsp+288h+phkResult], rax; phkResult
0x1400131e8  mov     r9d, 20019h; samDesired
0x1400131ee  xor     r8d, r8d; ulOptions
0x1400131f1  lea     rdx, aDefault; ".DEFAULT"
0x1400131f8  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1400131ff  call    cs:__imp_RegOpenKeyExW
0x140013205  test    eax, eax
0x140013207  jz      short loc_140013244
0x140013209  lea     rsi, WPP_GLOBAL_Control
0x140013210  mov     r10, cs:WPP_GLOBAL_Control
0x140013217  cmp     r10, rsi
0x14001321a  jz      short loc_140013268
0x14001321c  test    byte ptr [r10+1Ch], 1
0x140013221  jz      short loc_140013268
0x140013223  cmp     byte ptr [r10+19h], 2
0x140013228  jb      short loc_140013268
0x14001322a  mov     edx, 0Bh
0x14001322f  mov     r9d, eax
0x140013232  lea     r8, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids
0x140013239  mov     rcx, [r10+10h]
0x14001323d  call    WPP_SF_d
0x140013242  jmp     short loc_1400131D2
0x140013244  mov     r14d, 1
0x14001324a  mov     [rsp+288h+var_250], r14d
0x14001324f  mov     rcx, [rsp+288h+var_248]
0x140013254  jmp     loc_14001315E
0x140013259  cmp     [rsp+288h+Type], 4
0x14001325e  cmovz   ebx, dword ptr [rsp+288h+Data]
0x140013263  jmp     loc_1400131C0
0x140013268  mov     rcx, [rsp+288h+var_248]; hKey
0x14001326d  test    rcx, rcx
0x140013270  jnz     short loc_14001329D
0x140013272  cmp     r10, rsi
0x140013275  jnz     short loc_1400132B1
0x140013277  mov     [rdi], ebx
0x140013279  mov     rcx, [rsp+288h+var_28]
0x140013281  xor     rcx, rsp; StackCookie
0x140013284  call    __security_check_cookie
0x140013289  mov     rbx, [rsp+288h+arg_10]
0x140013291  add     rsp, 270h
0x140013298  pop     r14
0x14001329a  pop     rdi
0x14001329b  pop     rsi
0x14001329c  retn
0x14001329d  test    r14d, r14d
0x1400132a0  jz      short loc_140013272
0x1400132a2  call    cs:__imp_RegCloseKey
0x1400132a8  mov     r10, cs:WPP_GLOBAL_Control
0x1400132af  jmp     short loc_140013272
0x1400132b1  test    byte ptr [r10+1Ch], 1
0x1400132b6  jz      short loc_140013277
0x1400132b8  cmp     byte ptr [r10+19h], 4
0x1400132bd  jb      short loc_140013277
0x1400132bf  mov     edx, 0Ch
0x1400132c4  mov     r9d, ebx
0x1400132c7  lea     r8, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids
0x1400132ce  mov     rcx, [r10+10h]
0x1400132d2  call    WPP_SF_d
0x1400132d7  jmp     short loc_140013277
0x14009d670  push    rbp
0x14009d672  sub     rsp, 30h
0x14009d676  mov     rbp, rdx
0x14009d679  mov     rcx, [rbp+40h]; hKey
0x14009d67d  test    rcx, rcx
0x14009d680  jz      short loc_14009D68F
0x14009d682  cmp     dword ptr [rbp+38h], 0
0x14009d686  jz      short loc_14009D68F
0x14009d688  call    cs:__imp_RegCloseKey
0x14009d68e  nop
0x14009d68f  add     rsp, 30h
0x14009d693  pop     rbp
0x14009d694  retn
```
