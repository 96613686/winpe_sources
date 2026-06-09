# IsDeviceChild

- ea: `0x1800086c0`
- end: `0x180008be2`
- name: `IsDeviceChild`
- size: `1314`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000aba0`

## callees

- `0x1800086c0`
- `0x180008bf0`
- `0x18000a210`
- `0x180012130`
- `0x180013590`
- `0x180018970`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008848`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008922`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008ab2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008ba4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018ae0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018afe`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018b1c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018b3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008848`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008922`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008ab2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008ba4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018ae0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018afe`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018b1c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018b3a`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800089f7`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180008adb`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800089f7`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180008adb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800087de`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800088b4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008a3f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008b34`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800087de`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800088b4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008a3f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008b34`

## pseudocode

```c
__int64 __fastcall IsDeviceChild(__int64 a1)
{
  unsigned int v2; // r14d
  const WCHAR *v3; // rsi
  unsigned int v4; // r12d
  __int64 v5; // rax
  const WCHAR *v6; // r9
  __int64 v7; // rdx
  WCHAR *v8; // r8
  WCHAR *v9; // rcx
  PVOID i; // rbx
  int v12; // eax
  __int64 v13; // rdx
  void *v14; // rcx
  PVOID *j; // rbx
  PVOID v16; // rdi
  int v17; // eax
  __int64 v18; // rdx
  void *v19; // rcx
  __int64 v20; // rcx
  BYTE *v21; // rdx
  __int64 v22; // r8
  WCHAR *v23; // r9
  WCHAR *v24; // rcx
  PVOID k; // rbx
  unsigned int v26; // eax
  __int64 v27; // rdx
  void *v28; // rcx
  PVOID *m; // rbx
  PVOID v30; // rdi
  unsigned int v31; // eax
  __int64 v32; // rdx
  void *v33; // rcx
  ULONG v34; // [rsp+40h] [rbp-368h] BYREF
  int v35; // [rsp+44h] [rbp-364h]
  DEVPROPTYPE PropertyType; // [rsp+48h] [rbp-360h] BYREF
  WCHAR String1[200]; // [rsp+50h] [rbp-358h] BYREF
  BYTE PropertyBuffer[400]; // [rsp+1E0h] [rbp-1C8h] BYREF

  PropertyType = 0;
  v34 = 0;
  v2 = 0;
  v3 = *(const WCHAR **)(a1 + 32);
  v4 = *(_DWORD *)(a1 + 40);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids, v3);
  v5 = 2147483646;
  v6 = v3;
  v7 = 200;
  v8 = String1;
  do
  {
    if ( !v5 )
      break;
    if ( !*v6 )
      break;
    *v8++ = *v6++;
    --v5;
    --v7;
  }
  while ( v7 );
  v9 = v8 - 1;
  if ( v7 )
    v9 = v8;
  *v9 = 0;
  if ( v7 )
  {
    pSetupBeginSynchronizedAccess(&Handles);
    for ( i = ServerInstallList; i != (PVOID)a1; i = *(PVOID *)i )
    {
      if ( v4 != -1 )
      {
        v12 = *((_DWORD *)i + 10);
        if ( v12 != -1 && v12 != v4 )
          continue;
      }
      if ( CompareStringOrdinal(v3, -1, *((LPCWCH *)i + 4), -1, 1) == 2 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            11,
            WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids,
            *((_QWORD *)i + 4));
        }
        if ( (Microsoft_Windows_UserPnpEnableBits & 1) != 0 )
          McTemplateU0zz_EtwEventWriteTransfer(v14, v13, v3, *((_QWORD *)i + 4));
        v2 = 1;
        v35 = 1;
        break;
      }
    }
    ReleaseMutex(hMutex);
    if ( !v2 )
    {
      pSetupBeginSynchronizedAccess(&qword_1800239B0);
      for ( j = (PVOID *)ServerInstallThreadIdList; j != &ServerInstallThreadIdList; j = (PVOID *)*j )
      {
        v16 = j[3];
        if ( v16 )
        {
          if ( v4 == -1 || (v17 = *((_DWORD *)v16 + 10), v17 == -1) || v17 == v4 )
          {
            if ( CompareStringOrdinal(v3, -1, *((LPCWCH *)v16 + 4), -1, 1) == 2 )
            {
              v19 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
              {
                WPP_SF_S(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  12,
                  WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids,
                  *((_QWORD *)v16 + 4));
              }
              if ( (Microsoft_Windows_UserPnpEnableBits & 1) != 0 )
                McTemplateU0zz_EtwEventWriteTransfer(v19, v18, v3, *((_QWORD *)v16 + 4));
              v2 = 1;
              v35 = 1;
              break;
            }
          }
        }
      }
      ReleaseMutex(qword_1800239B8);
      while ( !v2 )
      {
        v34 = 400;
        if ( (unsigned int)PnpGetObjectProp(String1, &PropertyType, PropertyBuffer, &v34)
          || PropertyType != 18
          || v34 > 0x190 )
        {
          break;
        }
        v20 = 2147483646;
        v21 = PropertyBuffer;
        v22 = 200;
        v23 = String1;
        do
        {
          if ( !v20 )
            break;
          if ( !*(_WORD *)v21 )
            break;
          *v23++ = *(_WORD *)v21;
          v21 += 2;
          --v20;
          --v22;
        }
        while ( v22 );
        v24 = v23 - 1;
        if ( v22 )
          v24 = v23;
        *v24 = 0;
        if ( !v22 )
          break;
        WaitForMultipleObjectsEx(2u, &Handles, 0, 0xFFFFFFFF, 0);
        for ( k = ServerInstallList; k != (PVOID)a1; k = *(PVOID *)k )
        {
          if ( v4 != -1 )
          {
            v26 = *((_DWORD *)k + 10);
            if ( v26 != -1 && v26 >= v4 )
              continue;
          }
          if ( CompareStringOrdinal(String1, -1, *((LPCWCH *)k + 4), -1, 1) == 2 )
          {
            v28 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
            {
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                13,
                WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids,
                *((_QWORD *)k + 4));
            }
            if ( (Microsoft_Windows_UserPnpEnableBits & 1) != 0 )
              McTemplateU0zz_EtwEventWriteTransfer(v28, v27, String1, *((_QWORD *)k + 4));
            v2 = 1;
            v35 = 1;
            break;
          }
        }
        ReleaseMutex(hMutex);
        if ( v2 )
          break;
        WaitForMultipleObjectsEx(2u, &qword_1800239B0, 0, 0xFFFFFFFF, 0);
        for ( m = (PVOID *)ServerInstallThreadIdList; m != &ServerInstallThreadIdList; m = (PVOID *)*m )
        {
          v30 = m[3];
          if ( v30 )
          {
            if ( v4 == -1 || (v31 = *((_DWORD *)v30 + 10), v31 == -1) || v31 < v4 )
            {
              if ( CompareStringOrdinal(String1, -1, *((LPCWCH *)v30 + 4), -1, 1) == 2 )
              {
                v33 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
                {
                  WPP_SF_S(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    14,
                    WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids,
                    *((_QWORD *)v30 + 4));
                }
                if ( (Microsoft_Windows_UserPnpEnableBits & 1) != 0 )
                  McTemplateU0zz_EtwEventWriteTransfer(v33, v32, String1, *((_QWORD *)v30 + 4));
                v2 = 1;
                v35 = 1;
                break;
              }
            }
          }
        }
        ReleaseMutex(qword_1800239B8);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800086c0  mov     [rsp+arg_8], rbx
0x1800086c5  mov     [rsp+arg_10], rsi
0x1800086ca  push    rdi
0x1800086cb  push    r12
0x1800086cd  push    r13
0x1800086cf  push    r14
0x1800086d1  push    r15
0x1800086d3  sub     rsp, 380h
0x1800086da  mov     rax, cs:__security_cookie
0x1800086e1  xor     rax, rsp
0x1800086e4  mov     [rsp+3A8h+var_38], rax
0x1800086ec  mov     r15, rcx
0x1800086ef  xor     r13d, r13d
0x1800086f2  mov     [rsp+3A8h+PropertyType], r13d
0x1800086f7  mov     [rsp+3A8h+var_368], r13d
0x1800086fc  mov     r14d, r13d
0x1800086ff  mov     rsi, [rcx+20h]
0x180008703  mov     r12d, [rcx+28h]
0x180008707  lea     rdi, WPP_GLOBAL_Control
0x18000870e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008715  cmp     rcx, rdi
0x180008718  jnz     loc_180008BB8
0x18000871e  mov     eax, 7FFFFFFEh
0x180008723  mov     r9, rsi
0x180008726  mov     edx, 0C8h
0x18000872b  lea     r8, [rsp+3A8h+String1]
0x180008730  test    rax, rax
0x180008733  jz      short loc_180008753
0x180008735  movzx   ecx, word ptr [r9]
0x180008739  test    cx, cx
0x18000873c  jz      short loc_180008753
0x18000873e  mov     [r8], cx
0x180008742  add     r8, 2
0x180008746  add     r9, 2
0x18000874a  dec     rax
0x18000874d  sub     rdx, 1
0x180008751  jnz     short loc_180008730
0x180008753  lea     rcx, [r8-2]
0x180008757  test    rdx, rdx
0x18000875a  cmovnz  rcx, r8
0x18000875e  mov     eax, r13d
0x180008761  mov     [rcx], ax
0x180008764  jnz     short loc_180008796
0x180008766  mov     eax, r14d
0x180008769  mov     rcx, [rsp+3A8h+var_38]
0x180008771  xor     rcx, rsp; StackCookie
0x180008774  call    __security_check_cookie
0x180008779  lea     r11, [rsp+3A8h+var_28]
0x180008781  mov     rbx, [r11+38h]
0x180008785  mov     rsi, [r11+40h]
0x180008789  mov     rsp, r11
0x18000878c  pop     r15
0x18000878e  pop     r14
0x180008790  pop     r13
0x180008792  pop     r12
0x180008794  pop     rdi
0x180008795  retn
0x180008796  lea     rcx, Handles; lpHandles
0x18000879d  call    pSetupBeginSynchronizedAccess
0x1800087a2  nop
0x1800087a3  mov     rbx, cs:ServerInstallList
0x1800087aa  cmp     rbx, r15
0x1800087ad  jz      loc_180008841
0x1800087b3  cmp     r12d, 0FFFFFFFFh
0x1800087b7  jz      short loc_1800087C6
0x1800087b9  mov     eax, [rbx+28h]
0x1800087bc  cmp     eax, 0FFFFFFFFh
0x1800087bf  jz      short loc_1800087C6
0x1800087c1  cmp     eax, r12d
0x1800087c4  jnz     short loc_180008839
0x1800087c6  mov     [rsp+3A8h+bIgnoreCase], 1; bIgnoreCase
0x1800087ce  mov     r9d, 0FFFFFFFFh; cchCount2
0x1800087d4  mov     r8, [rbx+20h]; lpString2
0x1800087d8  mov     edx, r9d; cchCount1
0x1800087db  mov     rcx, rsi; lpString1
0x1800087de  call    cs:__imp_CompareStringOrdinal
0x1800087e4  cmp     eax, 2
0x1800087e7  jnz     short loc_180008839
0x1800087e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800087f0  cmp     rcx, rdi
0x1800087f3  jz      short loc_180008817
0x1800087f5  test    dword ptr [rcx+1Ch], 800000h
0x1800087fc  jz      short loc_180008817
0x1800087fe  mov     edx, 0Bh
0x180008803  mov     r9, [rbx+20h]
0x180008807  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x18000880e  mov     rcx, [rcx+10h]
0x180008812  call    WPP_SF_S
0x180008817  test    cs:Microsoft_Windows_UserPnpEnableBits, 1
0x18000881e  jz      short loc_18000882C
0x180008820  mov     r9, [rbx+20h]
0x180008824  mov     r8, rsi
0x180008827  call    McTemplateU0zz_EtwEventWriteTransfer
0x18000882c  mov     r14d, 1
0x180008832  mov     [rsp+3A8h+var_364], r14d
0x180008837  jmp     short loc_180008841
0x180008839  mov     rbx, [rbx]
0x18000883c  jmp     loc_1800087AA
0x180008841  mov     rcx, cs:hMutex; hMutex
0x180008848  call    cs:__imp_ReleaseMutex
0x18000884e  test    r14d, r14d
0x180008851  jnz     loc_180008766
0x180008857  lea     rcx, qword_1800239B0; lpHandles
0x18000885e  call    pSetupBeginSynchronizedAccess
0x180008863  nop
0x180008864  mov     rbx, cs:ServerInstallThreadIdList
0x18000886b  lea     rdi, ServerInstallThreadIdList
0x180008872  cmp     rbx, rdi
0x180008875  jz      loc_18000891B
0x18000887b  mov     rdi, [rbx+18h]
0x18000887f  test    rdi, rdi
0x180008882  jz      short loc_180008897
0x180008884  cmp     r12d, 0FFFFFFFFh
0x180008888  jz      short loc_18000889C
0x18000888a  mov     eax, [rdi+28h]
0x18000888d  cmp     eax, 0FFFFFFFFh
0x180008890  jz      short loc_18000889C
0x180008892  cmp     eax, r12d
0x180008895  jz      short loc_18000889C
0x180008897  mov     rbx, [rbx]
0x18000889a  jmp     short loc_18000886B
0x18000889c  mov     [rsp+3A8h+bIgnoreCase], 1; bIgnoreCase
0x1800088a4  mov     r9d, 0FFFFFFFFh; cchCount2
0x1800088aa  mov     r8, [rdi+20h]; lpString2
0x1800088ae  mov     edx, r9d; cchCount1
0x1800088b1  mov     rcx, rsi; lpString1
0x1800088b4  call    cs:__imp_CompareStringOrdinal
0x1800088ba  cmp     eax, 2
0x1800088bd  jnz     short loc_180008897
0x1800088bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800088c6  lea     rax, WPP_GLOBAL_Control
0x1800088cd  cmp     rcx, rax
0x1800088d0  jz      short loc_1800088F4
0x1800088d2  test    dword ptr [rcx+1Ch], 800000h
0x1800088d9  jz      short loc_1800088F4
0x1800088db  mov     edx, 0Ch
0x1800088e0  mov     r9, [rdi+20h]
0x1800088e4  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x1800088eb  mov     rcx, [rcx+10h]
0x1800088ef  call    WPP_SF_S
0x1800088f4  test    cs:Microsoft_Windows_UserPnpEnableBits, 1
0x1800088fb  jz      short loc_180008909
0x1800088fd  mov     r9, [rdi+20h]
0x180008901  mov     r8, rsi
0x180008904  call    McTemplateU0zz_EtwEventWriteTransfer
0x180008909  mov     r14d, 1
0x18000890f  mov     [rsp+3A8h+var_364], r14d
0x180008914  lea     rdi, ServerInstallThreadIdList
0x18000891b  mov     rcx, cs:qword_1800239B8; hMutex
0x180008922  call    cs:__imp_ReleaseMutex
0x180008928  test    r14d, r14d
0x18000892b  jnz     loc_180008766
0x180008931  mov     [rsp+3A8h+var_368], 190h
0x180008939  lea     rax, [rsp+3A8h+var_368]
0x18000893e  mov     [rsp+3A8h+var_378], rax; PULONG
0x180008943  lea     rax, [rsp+3A8h+var_1C8]
0x18000894b  mov     [rsp+3A8h+PropertyBuffer], rax; PropertyBuffer
0x180008950  lea     rax, [rsp+3A8h+PropertyType]
0x180008955  mov     qword ptr [rsp+3A8h+bIgnoreCase], rax; PropertyType
0x18000895a  lea     r9, DEVPKEY_Device_Parent
0x180008961  lea     rcx, [rsp+3A8h+String1]; pDeviceID
0x180008966  call    PnpGetObjectProp
0x18000896b  test    eax, eax
0x18000896d  jnz     loc_180008766
0x180008973  cmp     [rsp+3A8h+PropertyType], 12h
0x180008978  jnz     loc_180008766
0x18000897e  cmp     [rsp+3A8h+var_368], 190h
0x180008986  ja      loc_180008766
0x18000898c  mov     ecx, 7FFFFFFEh
0x180008991  lea     rdx, [rsp+3A8h+var_1C8]
0x180008999  mov     r8d, 0C8h
0x18000899f  lea     r9, [rsp+3A8h+String1]
0x1800089a4  test    rcx, rcx
0x1800089a7  jz      short loc_1800089C6
0x1800089a9  movzx   eax, word ptr [rdx]
0x1800089ac  test    ax, ax
0x1800089af  jz      short loc_1800089C6
0x1800089b1  mov     [r9], ax
0x1800089b5  add     r9, 2
0x1800089b9  add     rdx, 2
0x1800089bd  dec     rcx
0x1800089c0  sub     r8, 1
0x1800089c4  jnz     short loc_1800089A4
0x1800089c6  lea     rcx, [r9-2]
0x1800089ca  test    r8, r8
0x1800089cd  cmovnz  rcx, r9
0x1800089d1  mov     eax, r13d
0x1800089d4  mov     [rcx], ax
0x1800089d7  jz      loc_180008766
0x1800089dd  mov     [rsp+3A8h+bIgnoreCase], r13d; bAlertable
0x1800089e2  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x1800089e8  xor     r8d, r8d; bWaitAll
0x1800089eb  lea     rdx, Handles; lpHandles
0x1800089f2  mov     ecx, 2; nCount
0x1800089f7  call    cs:__imp_WaitForMultipleObjectsEx
0x1800089fd  nop
0x1800089fe  mov     rbx, cs:ServerInstallList
0x180008a05  cmp     rbx, r15
0x180008a08  jz      loc_180008AAB
0x180008a0e  cmp     r12d, 0FFFFFFFFh
0x180008a12  jz      short loc_180008A25
0x180008a14  mov     eax, [rbx+28h]
0x180008a17  cmp     eax, 0FFFFFFFFh
0x180008a1a  jz      short loc_180008A25
0x180008a1c  cmp     eax, r12d
0x180008a1f  jnb     loc_180008AA3
0x180008a25  mov     [rsp+3A8h+bIgnoreCase], 1; bIgnoreCase
0x180008a2d  mov     r9d, 0FFFFFFFFh; cchCount2
0x180008a33  mov     r8, [rbx+20h]; lpString2
0x180008a37  mov     edx, r9d; cchCount1
0x180008a3a  lea     rcx, [rsp+3A8h+String1]; lpString1
0x180008a3f  call    cs:__imp_CompareStringOrdinal
0x180008a45  cmp     eax, 2
0x180008a48  jnz     short loc_180008AA3
0x180008a4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a51  lea     rax, WPP_GLOBAL_Control
0x180008a58  cmp     rcx, rax
0x180008a5b  jz      short loc_180008A7F
0x180008a5d  test    dword ptr [rcx+1Ch], 800000h
0x180008a64  jz      short loc_180008A7F
0x180008a66  mov     edx, 0Dh
0x180008a6b  mov     r9, [rbx+20h]
0x180008a6f  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x180008a76  mov     rcx, [rcx+10h]
0x180008a7a  call    WPP_SF_S
0x180008a7f  test    cs:Microsoft_Windows_UserPnpEnableBits, 1
0x180008a86  jz      short loc_180008A96
0x180008a88  mov     r9, [rbx+20h]
0x180008a8c  lea     r8, [rsp+3A8h+String1]
0x180008a91  call    McTemplateU0zz_EtwEventWriteTransfer
0x180008a96  mov     r14d, 1
0x180008a9c  mov     [rsp+3A8h+var_364], r14d
0x180008aa1  jmp     short loc_180008AAB
0x180008aa3  mov     rbx, [rbx]
0x180008aa6  jmp     loc_180008A05
0x180008aab  mov     rcx, cs:hMutex; hMutex
0x180008ab2  call    cs:__imp_ReleaseMutex
0x180008ab8  test    r14d, r14d
0x180008abb  jnz     loc_180008766
0x180008ac1  mov     [rsp+3A8h+bIgnoreCase], r13d; bAlertable
0x180008ac6  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x180008acc  xor     r8d, r8d; bWaitAll
0x180008acf  lea     rdx, qword_1800239B0; lpHandles
0x180008ad6  mov     ecx, 2; nCount
0x180008adb  call    cs:__imp_WaitForMultipleObjectsEx
0x180008ae1  nop
0x180008ae2  mov     rbx, cs:ServerInstallThreadIdList
0x180008ae9  cmp     rbx, rdi
0x180008aec  jz      loc_180008B9D
0x180008af2  mov     rdi, [rbx+18h]
0x180008af6  test    rdi, rdi
0x180008af9  jz      short loc_180008B0E
0x180008afb  cmp     r12d, 0FFFFFFFFh
0x180008aff  jz      short loc_180008B1A
0x180008b01  mov     eax, [rdi+28h]
0x180008b04  cmp     eax, 0FFFFFFFFh
0x180008b07  jz      short loc_180008B1A
0x180008b09  cmp     eax, r12d
0x180008b0c  jb      short loc_180008B1A
0x180008b0e  mov     rbx, [rbx]
0x180008b11  lea     rdi, ServerInstallThreadIdList
0x180008b18  jmp     short loc_180008AE9
0x180008b1a  mov     [rsp+3A8h+bIgnoreCase], 1; bIgnoreCase
0x180008b22  mov     r9d, 0FFFFFFFFh; cchCount2
0x180008b28  mov     r8, [rdi+20h]; lpString2
0x180008b2c  mov     edx, r9d; cchCount1
0x180008b2f  lea     rcx, [rsp+3A8h+String1]; lpString1
0x180008b34  call    cs:__imp_CompareStringOrdinal
0x180008b3a  cmp     eax, 2
0x180008b3d  jnz     short loc_180008B0E
0x180008b3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b46  lea     rax, WPP_GLOBAL_Control
0x180008b4d  cmp     rcx, rax
0x180008b50  jz      short loc_180008B74
0x180008b52  test    dword ptr [rcx+1Ch], 800000h
0x180008b59  jz      short loc_180008B74
0x180008b5b  mov     edx, 0Eh
0x180008b60  mov     r9, [rdi+20h]
0x180008b64  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x180008b6b  mov     rcx, [rcx+10h]
0x180008b6f  call    WPP_SF_S
0x180008b74  test    cs:Microsoft_Windows_UserPnpEnableBits, 1
0x180008b7b  jz      short loc_180008B8B
0x180008b7d  mov     r9, [rdi+20h]
0x180008b81  lea     r8, [rsp+3A8h+String1]
0x180008b86  call    McTemplateU0zz_EtwEventWriteTransfer
0x180008b8b  mov     r14d, 1
0x180008b91  mov     [rsp+3A8h+var_364], r14d
0x180008b96  lea     rdi, ServerInstallThreadIdList
0x180008b9d  mov     rcx, cs:qword_1800239B8; hMutex
0x180008ba4  call    cs:__imp_ReleaseMutex
0x180008baa  test    r14d, r14d
0x180008bad  jz      loc_180008931
0x180008bb3  jmp     loc_180008766
0x180008bb8  test    dword ptr [rcx+1Ch], 800000h
0x180008bbf  jz      loc_18000871E
0x180008bc5  mov     edx, 0Ah
0x180008bca  mov     r9, rsi
0x180008bcd  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x180008bd4  mov     rcx, [rcx+10h]
  ... truncated ...
```
