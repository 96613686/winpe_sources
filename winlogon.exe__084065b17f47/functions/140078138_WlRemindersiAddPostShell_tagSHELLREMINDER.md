# WlRemindersiAddPostShell(_tagSHELLREMINDER *)

- ea: `0x140078138`
- end: `0x1400784da`
- name: `?WlRemindersiAddPostShell@@YAKPEAU_tagSHELLREMINDER@@@Z`
- size: `930`
- prototype: `unsigned int __fastcall(struct _tagSHELLREMINDER *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140077464`

## callees

- `0x140026970`
- `0x14005f43c`
- `0x140078138`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400782a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400782ed`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140078331`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140078375`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400783b6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400783e3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14007840b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140078433`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14007845b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400782a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400782ed`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140078331`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140078375`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400783b6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400783e3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14007840b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140078433`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14007845b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14007818d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14007821e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14007818d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14007821e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400784ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400784c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009fbea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009fbfd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400784ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400784c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009fbea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009fbfd`

## pseudocode

```c
__int64 __fastcall WlRemindersiAddPostShell(struct _tagSHELLREMINDER *a1)
{
  unsigned int v2; // esi
  CUser *v3; // rcx
  int v4; // edx
  const WCHAR *v5; // r9
  const BYTE *v6; // rcx
  __int64 v7; // rdi
  __int64 v8; // rax
  const BYTE *v9; // rcx
  __int64 v10; // rax
  const BYTE *v11; // rcx
  __int64 v12; // rax
  const BYTE *v13; // rcx
  __int64 v14; // rax
  const BYTE *v15; // rcx
  HKEY phkResult; // [rsp+88h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+18h] BYREF

  hKey = 0;
  phkResult = 0;
  v2 = RegCreateKeyExW(
         *((HKEY *)qword_1400D2560 + 29),
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\PostBootReminders",
         0,
         0,
         0,
         0x20006u,
         0,
         &hKey,
         0);
  if ( v2 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = 13;
      v5 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\PostBootReminders";
LABEL_6:
      WPP_SF_Sl(*((_QWORD *)v3 + 2), v4, (unsigned int)WPP_45f944bba9fd33a68794881c2280ffd4_Traceguids, (_DWORD)v5, v2);
    }
  }
  else
  {
    v2 = RegCreateKeyExW(hKey, *((LPCWSTR *)a1 + 1), 0, 0, 0, 0x20006u, 0, &phkResult, 0);
    if ( v2 )
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v4 = 14;
        v5 = (const WCHAR *)*((_QWORD *)a1 + 1);
        goto LABEL_6;
      }
    }
    else
    {
      v6 = (const BYTE *)*((_QWORD *)a1 + 2);
      v7 = -1;
      if ( v6 )
      {
        v8 = -1;
        do
          ++v8;
        while ( *(_WORD *)&v6[2 * v8] );
        RegSetValueExW(phkResult, L"Title", 0, 1u, v6, 2 * v8 + 2);
      }
      v9 = (const BYTE *)*((_QWORD *)a1 + 3);
      if ( v9 )
      {
        v10 = -1;
        do
          ++v10;
        while ( *(_WORD *)&v9[2 * v10] );
        RegSetValueExW(phkResult, L"Text", 0, 1u, v9, 2 * v10 + 2);
      }
      v11 = (const BYTE *)*((_QWORD *)a1 + 4);
      if ( v11 )
      {
        v12 = -1;
        do
          ++v12;
        while ( *(_WORD *)&v11[2 * v12] );
        RegSetValueExW(phkResult, L"ToolTip", 0, 1u, v11, 2 * v12 + 2);
      }
      v13 = (const BYTE *)*((_QWORD *)a1 + 5);
      if ( v13 )
      {
        v14 = -1;
        do
          ++v14;
        while ( *(_WORD *)&v13[2 * v14] );
        RegSetValueExW(phkResult, L"IconResource", 0, 1u, v13, 2 * v14 + 2);
      }
      v15 = (const BYTE *)*((_QWORD *)a1 + 6);
      if ( v15 )
      {
        do
          ++v7;
        while ( *(_WORD *)&v15[2 * v7] );
        RegSetValueExW(phkResult, L"ShellExecute", 0, 1u, v15, 2 * v7 + 2);
      }
      RegSetValueExW(phkResult, L"ShowTime", 0, 4u, (const BYTE *)a1 + 64, 4u);
      RegSetValueExW(phkResult, L"RetryInterval", 0, 4u, (const BYTE *)a1 + 68, 4u);
      RegSetValueExW(phkResult, L"RetryCount", 0, 4u, (const BYTE *)a1 + 72, 4u);
      RegSetValueExW(phkResult, L"TypeFlags", 0, 4u, (const BYTE *)a1 + 76, 4u);
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          (unsigned int)WPP_45f944bba9fd33a68794881c2280ffd4_Traceguids,
          *((_QWORD *)a1 + 2),
          *((_QWORD *)a1 + 3));
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return v2;
}

```

## disassembly

```asm
0x140078138  mov     r11, rsp
0x14007813b  mov     [r11+8], rbx
0x14007813f  push    rsi
0x140078140  push    rdi
0x140078141  push    r15
0x140078143  sub     rsp, 60h
0x140078147  mov     rbx, rcx
0x14007814a  xor     r15d, r15d
0x14007814d  mov     [r11+18h], r15
0x140078151  mov     [r11+10h], r15
0x140078155  mov     [r11-38h], r15
0x140078159  lea     rax, [r11+18h]
0x14007815d  mov     [r11-40h], rax
0x140078161  mov     [r11-48h], r15
0x140078165  mov     edi, 20006h
0x14007816a  mov     [rsp+78h+samDesired], edi; samDesired
0x14007816e  mov     [r11-58h], r15d
0x140078172  xor     r9d, r9d; lpClass
0x140078175  xor     r8d, r8d; Reserved
0x140078178  lea     rdx, aSoftwareMicros_12; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14007817f  mov     rcx, cs:qword_1400D2560
0x140078186  mov     rcx, [rcx+0E8h]; hKey
0x14007818d  call    cs:__imp_RegCreateKeyExW
0x140078193  mov     esi, eax
0x140078195  mov     [rsp+78h+var_28], eax
0x140078199  test    eax, eax
0x14007819b  jz      short loc_1400781EC
0x14007819d  lea     rax, WPP_GLOBAL_Control
0x1400781a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400781ab  cmp     rcx, rax
0x1400781ae  jz      loc_1400784A1
0x1400781b4  test    byte ptr [rcx+1Ch], 20h
0x1400781b8  jz      loc_1400784A1
0x1400781be  cmp     byte ptr [rcx+19h], 2
0x1400781c2  jb      loc_1400784A1
0x1400781c8  lea     edx, [r15+0Dh]
0x1400781cc  lea     r9, aSoftwareMicros_12; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400781d3  mov     [rsp+78h+dwOptions], esi
0x1400781d7  lea     r8, WPP_45f944bba9fd33a68794881c2280ffd4_Traceguids
0x1400781de  mov     rcx, [rcx+10h]
0x1400781e2  call    WPP_SF_Sl
0x1400781e7  jmp     loc_1400784A1
0x1400781ec  mov     [rsp+78h+lpdwDisposition], r15; lpdwDisposition
0x1400781f1  lea     rax, [rsp+78h+arg_8]
0x1400781f9  mov     [rsp+78h+phkResult], rax; phkResult
0x1400781fe  mov     [rsp+78h+lpSecurityAttributes], r15; lpSecurityAttributes
0x140078203  mov     [rsp+78h+samDesired], edi; samDesired
0x140078207  mov     [rsp+78h+dwOptions], r15d; dwOptions
0x14007820c  xor     r9d, r9d; lpClass
0x14007820f  xor     r8d, r8d; Reserved
0x140078212  mov     rdx, [rbx+8]; lpSubKey
0x140078216  mov     rcx, [rsp+78h+hKey]; hKey
0x14007821e  call    cs:__imp_RegCreateKeyExW
0x140078224  mov     esi, eax
0x140078226  mov     [rsp+78h+var_28], eax
0x14007822a  test    eax, eax
0x14007822c  jz      short loc_140078267
0x14007822e  lea     rax, WPP_GLOBAL_Control
0x140078235  mov     rcx, cs:WPP_GLOBAL_Control
0x14007823c  cmp     rcx, rax
0x14007823f  jz      loc_1400784A1
0x140078245  test    byte ptr [rcx+1Ch], 20h
0x140078249  jz      loc_1400784A1
0x14007824f  cmp     byte ptr [rcx+19h], 2
0x140078253  jb      loc_1400784A1
0x140078259  mov     edx, 0Eh
0x14007825e  mov     r9, [rbx+8]
0x140078262  jmp     loc_1400781D3
0x140078267  mov     rcx, [rbx+10h]
0x14007826b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14007826f  test    rcx, rcx
0x140078272  jz      short loc_1400782AF
0x140078274  mov     rax, rdi
0x140078277  inc     rax
0x14007827a  cmp     [rcx+rax*2], r15w
0x14007827f  jnz     short loc_140078277
0x140078281  lea     eax, ds:2[rax*2]
0x140078288  mov     [rsp+78h+samDesired], eax; cbData
0x14007828c  mov     qword ptr [rsp+78h+dwOptions], rcx; lpData
0x140078291  mov     r9d, 1; dwType
0x140078297  xor     r8d, r8d; Reserved
0x14007829a  lea     rdx, aTitle; "Title"
0x1400782a1  mov     rcx, [rsp+78h+arg_8]; hKey
0x1400782a9  call    cs:__imp_RegSetValueExW
0x1400782af  mov     rcx, [rbx+18h]
0x1400782b3  test    rcx, rcx
0x1400782b6  jz      short loc_1400782F3
0x1400782b8  mov     rax, rdi
0x1400782bb  inc     rax
0x1400782be  cmp     [rcx+rax*2], r15w
0x1400782c3  jnz     short loc_1400782BB
0x1400782c5  lea     eax, ds:2[rax*2]
0x1400782cc  mov     [rsp+78h+samDesired], eax; cbData
0x1400782d0  mov     qword ptr [rsp+78h+dwOptions], rcx; lpData
0x1400782d5  mov     r9d, 1; dwType
0x1400782db  xor     r8d, r8d; Reserved
0x1400782de  lea     rdx, aText; "Text"
0x1400782e5  mov     rcx, [rsp+78h+arg_8]; hKey
0x1400782ed  call    cs:__imp_RegSetValueExW
0x1400782f3  mov     rcx, [rbx+20h]
0x1400782f7  test    rcx, rcx
0x1400782fa  jz      short loc_140078337
0x1400782fc  mov     rax, rdi
0x1400782ff  inc     rax
0x140078302  cmp     [rcx+rax*2], r15w
0x140078307  jnz     short loc_1400782FF
0x140078309  lea     eax, ds:2[rax*2]
0x140078310  mov     [rsp+78h+samDesired], eax; cbData
0x140078314  mov     qword ptr [rsp+78h+dwOptions], rcx; lpData
0x140078319  mov     r9d, 1; dwType
0x14007831f  xor     r8d, r8d; Reserved
0x140078322  lea     rdx, aTooltip; "ToolTip"
0x140078329  mov     rcx, [rsp+78h+arg_8]; hKey
0x140078331  call    cs:__imp_RegSetValueExW
0x140078337  mov     rcx, [rbx+28h]
0x14007833b  test    rcx, rcx
0x14007833e  jz      short loc_14007837B
0x140078340  mov     rax, rdi
0x140078343  inc     rax
0x140078346  cmp     [rcx+rax*2], r15w
0x14007834b  jnz     short loc_140078343
0x14007834d  lea     eax, ds:2[rax*2]
0x140078354  mov     [rsp+78h+samDesired], eax; cbData
0x140078358  mov     qword ptr [rsp+78h+dwOptions], rcx; lpData
0x14007835d  mov     r9d, 1; dwType
0x140078363  xor     r8d, r8d; Reserved
0x140078366  lea     rdx, aIconresource; "IconResource"
0x14007836d  mov     rcx, [rsp+78h+arg_8]; hKey
0x140078375  call    cs:__imp_RegSetValueExW
0x14007837b  mov     rcx, [rbx+30h]
0x14007837f  test    rcx, rcx
0x140078382  jz      short loc_1400783BC
0x140078384  inc     rdi
0x140078387  cmp     [rcx+rdi*2], r15w
0x14007838c  jnz     short loc_140078384
0x14007838e  lea     eax, ds:2[rdi*2]
0x140078395  mov     [rsp+78h+samDesired], eax; cbData
0x140078399  mov     qword ptr [rsp+78h+dwOptions], rcx; lpData
0x14007839e  mov     r9d, 1; dwType
0x1400783a4  xor     r8d, r8d; Reserved
0x1400783a7  lea     rdx, aShellexecute; "ShellExecute"
0x1400783ae  mov     rcx, [rsp+78h+arg_8]; hKey
0x1400783b6  call    cs:__imp_RegSetValueExW
0x1400783bc  lea     rax, [rbx+40h]
0x1400783c0  mov     edi, 4
0x1400783c5  mov     [rsp+78h+samDesired], edi; cbData
0x1400783c9  mov     qword ptr [rsp+78h+dwOptions], rax; lpData
0x1400783ce  mov     r9d, edi; dwType
0x1400783d1  xor     r8d, r8d; Reserved
0x1400783d4  lea     rdx, aShowtime; "ShowTime"
0x1400783db  mov     rcx, [rsp+78h+arg_8]; hKey
0x1400783e3  call    cs:__imp_RegSetValueExW
0x1400783e9  lea     rax, [rbx+44h]
0x1400783ed  mov     [rsp+78h+samDesired], edi; cbData
0x1400783f1  mov     qword ptr [rsp+78h+dwOptions], rax; lpData
0x1400783f6  mov     r9d, edi; dwType
0x1400783f9  xor     r8d, r8d; Reserved
0x1400783fc  lea     rdx, aRetryinterval; "RetryInterval"
0x140078403  mov     rcx, [rsp+78h+arg_8]; hKey
0x14007840b  call    cs:__imp_RegSetValueExW
0x140078411  lea     rax, [rbx+48h]
0x140078415  mov     [rsp+78h+samDesired], edi; cbData
0x140078419  mov     qword ptr [rsp+78h+dwOptions], rax; lpData
0x14007841e  mov     r9d, edi; dwType
0x140078421  xor     r8d, r8d; Reserved
0x140078424  lea     rdx, aRetrycount; "RetryCount"
0x14007842b  mov     rcx, [rsp+78h+arg_8]; hKey
0x140078433  call    cs:__imp_RegSetValueExW
0x140078439  lea     rax, [rbx+4Ch]
0x14007843d  mov     [rsp+78h+samDesired], edi; cbData
0x140078441  mov     qword ptr [rsp+78h+dwOptions], rax; lpData
0x140078446  mov     r9d, edi; dwType
0x140078449  xor     r8d, r8d; Reserved
0x14007844c  lea     rdx, aTypeflags; "TypeFlags"
0x140078453  mov     rcx, [rsp+78h+arg_8]; hKey
0x14007845b  call    cs:__imp_RegSetValueExW
0x140078461  lea     rax, WPP_GLOBAL_Control
0x140078468  mov     rcx, cs:WPP_GLOBAL_Control
0x14007846f  cmp     rcx, rax
0x140078472  jz      short loc_1400784A1
0x140078474  test    byte ptr [rcx+1Ch], 20h
0x140078478  jz      short loc_1400784A1
0x14007847a  cmp     [rcx+19h], dil
0x14007847e  jb      short loc_1400784A1
0x140078480  lea     edx, [rdi+0Bh]
0x140078483  mov     rax, [rbx+18h]
0x140078487  mov     qword ptr [rsp+78h+dwOptions], rax
0x14007848c  mov     r9, [rbx+10h]
0x140078490  lea     r8, WPP_45f944bba9fd33a68794881c2280ffd4_Traceguids
0x140078497  mov     rcx, [rcx+10h]
0x14007849b  call    WPP_SF_SS
0x1400784a0  nop
0x1400784a1  mov     rcx, [rsp+78h+hKey]; hKey
0x1400784a9  test    rcx, rcx
0x1400784ac  jz      short loc_1400784B4
0x1400784ae  call    cs:__imp_RegCloseKey
0x1400784b4  mov     rcx, [rsp+78h+arg_8]; hKey
0x1400784bc  test    rcx, rcx
0x1400784bf  jz      short loc_1400784C7
0x1400784c1  call    cs:__imp_RegCloseKey
0x1400784c7  mov     eax, esi
0x1400784c9  mov     rbx, [rsp+78h+arg_0]
0x1400784d1  add     rsp, 60h
0x1400784d5  pop     r15
0x1400784d7  pop     rdi
0x1400784d8  pop     rsi
0x1400784d9  retn
0x14009fbd5  push    rbp
0x14009fbd7  sub     rsp, 50h
0x14009fbdb  mov     rbp, rdx
0x14009fbde  mov     rcx, [rbp+90h]; hKey
0x14009fbe5  test    rcx, rcx
0x14009fbe8  jz      short loc_14009FBF1
0x14009fbea  call    cs:__imp_RegCloseKey
0x14009fbf0  nop
0x14009fbf1  mov     rcx, [rbp+88h]; hKey
0x14009fbf8  test    rcx, rcx
0x14009fbfb  jz      short loc_14009FC04
0x14009fbfd  call    cs:__imp_RegCloseKey
0x14009fc03  nop
0x14009fc04  add     rsp, 50h
0x14009fc08  pop     rbp
0x14009fc09  retn
```
