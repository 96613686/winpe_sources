# CSecurityVerificationManager::GetIsWHQLSigned(ushort const *)

- ea: `0x180038050`
- end: `0x18003818e`
- name: `?GetIsWHQLSigned@CSecurityVerificationManager@@QEAAJPEBG@Z`
- size: `318`
- prototype: `__int64 __fastcall(CSecurityVerificationManager *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800337d0`

## callees

- `0x180029158`
- `0x180038050`
- `0x180038254`
- `0x18003fbf2`
- `0x18003fc30`

## import_xrefs

- `WINTRUST!WinVerifyTrust` at `0x18003812c`
- `WINTRUST!WinVerifyTrust` at `0x180038145`
- `WINTRUST!WinVerifyTrust` at `0x18003812c`
- `WINTRUST!WinVerifyTrust` at `0x180038145`

## pseudocode

```c
__int64 __fastcall CSecurityVerificationManager::GetIsWHQLSigned(
        CSecurityVerificationManager *this,
        const unsigned __int16 *a2)
{
  LONG v3; // eax
  unsigned int v4; // edi
  int v5; // r8d
  __int128 v7; // [rsp+30h] [rbp-69h] BYREF
  __int128 v8; // [rsp+40h] [rbp-59h]
  _DWORD pWVTData[10]; // [rsp+50h] [rbp-49h] BYREF
  __int128 *v10; // [rsp+78h] [rbp-21h]
  int v11; // [rsp+80h] [rbp-19h]
  int v12; // [rsp+98h] [rbp-1h]
  GUID pgActionID; // [rsp+B0h] [rbp+17h] BYREF

  memset_0(pWVTData, 0, 0x58u);
  pgActionID.Data1 = -145692989;
  v7 = 0;
  *(_DWORD *)&pgActionID.Data2 = 298924270;
  v8 = 0;
  *(_DWORD *)pgActionID.Data4 = -1073683067;
  *(_DWORD *)&pgActionID.Data4[4] = -292175281;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, a2);
  memset_0(pWVTData, 0, 0x58u);
  pWVTData[0] = 88;
  pWVTData[8] = 1;
  v11 = 1;
  pWVTData[6] = 2;
  v10 = &v7;
  v12 = 4160;
  *(_QWORD *)&v7 = 32;
  v8 = 0;
  *((_QWORD *)&v7 + 1) = a2;
  v3 = WinVerifyTrust(0, &pgActionID, pWVTData);
  v11 = 2;
  v4 = v3;
  WinVerifyTrust(0, &pgActionID, pWVTData);
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v5, v4, (__int64)a2);
  return v4;
}

```

## disassembly

```asm
0x180038050  push    rbp
0x180038052  push    rbx
0x180038053  push    rdi
0x180038054  push    r14
0x180038056  lea     rbp, [rsp-3Fh]
0x18003805b  sub     rsp, 0D8h
0x180038062  mov     rax, cs:__security_cookie
0x180038069  xor     rax, rsp
0x18003806c  mov     [rbp+57h+var_30], rax
0x180038070  mov     rbx, rdx
0x180038073  lea     rcx, [rbp+57h+pWVTData]; void *
0x180038077  mov     edi, 58h ; 'X'
0x18003807c  xor     edx, edx; Val
0x18003807e  mov     r8d, edi; Size
0x180038081  call    memset_0
0x180038086  xorps   xmm0, xmm0
0x180038089  mov     [rbp+57h+pgActionID.Data1], 0F750E6C3h
0x180038090  movups  [rbp+57h+var_C0], xmm0
0x180038094  mov     dword ptr [rbp+57h+pgActionID.Data2], 11D138EEh
0x18003809b  movups  [rbp+57h+var_B0], xmm0
0x18003809f  mov     dword ptr [rbp+57h+pgActionID.Data4], 0C000E585h
0x1800380a6  mov     dword ptr [rbp+57h+pgActionID.Data4+4], 0EE95C24Fh
0x1800380ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800380b4  lea     r14, WPP_GLOBAL_Control
0x1800380bb  cmp     rcx, r14
0x1800380be  jz      short loc_1800380DC
0x1800380c0  test    byte ptr [rcx+1Ch], 4
0x1800380c4  jz      short loc_1800380DC
0x1800380c6  mov     rcx, [rcx+10h]
0x1800380ca  lea     edx, [rdi-46h]
0x1800380cd  mov     r9, rbx
0x1800380d0  lea     r8, WPP_58c7d8ca840131a6c20521327163655c_Traceguids
0x1800380d7  call    WPP_SF_S
0x1800380dc  mov     r8, rdi; Size
0x1800380df  lea     rcx, [rbp+57h+pWVTData]; void *
0x1800380e3  xor     edx, edx; Val
0x1800380e5  call    memset_0
0x1800380ea  mov     eax, 1
0x1800380ef  mov     [rbp+57h+pWVTData], edi
0x1800380f2  mov     [rbp+57h+var_80], eax
0x1800380f5  lea     r8, [rbp+57h+pWVTData]; pWVTData
0x1800380f9  mov     [rbp+57h+var_70], eax
0x1800380fc  lea     rdx, [rbp+57h+pgActionID]; pgActionID
0x180038100  lea     rax, [rbp+57h+var_C0]
0x180038104  mov     [rbp+57h+var_88], 2
0x18003810b  xorps   xmm0, xmm0
0x18003810e  mov     [rbp+57h+var_78], rax
0x180038112  xor     ecx, ecx; hwnd
0x180038114  mov     [rbp+57h+var_58], 1040h
0x18003811b  mov     qword ptr [rbp+57h+var_C0], 20h ; ' '
0x180038123  movdqu  [rbp+57h+var_B0], xmm0
0x180038128  mov     qword ptr [rbp+57h+var_C0+8], rbx
0x18003812c  call    cs:__imp_WinVerifyTrust
0x180038132  lea     r8, [rbp+57h+pWVTData]; pWVTData
0x180038136  mov     [rbp+57h+var_70], 2
0x18003813d  lea     rdx, [rbp+57h+pgActionID]; pgActionID
0x180038141  xor     ecx, ecx; hwnd
0x180038143  mov     edi, eax
0x180038145  call    cs:__imp_WinVerifyTrust
0x18003814b  mov     rcx, cs:WPP_GLOBAL_Control
0x180038152  cmp     rcx, r14
0x180038155  jz      short loc_180038173
0x180038157  test    byte ptr [rcx+1Ch], 4
0x18003815b  jz      short loc_180038173
0x18003815d  mov     rcx, [rcx+10h]
0x180038161  mov     edx, 13h
0x180038166  mov     r9d, edi
0x180038169  mov     [rsp+0F0h+var_D0], rbx
0x18003816e  call    WPP_SF_dS
0x180038173  mov     eax, edi
0x180038175  mov     rcx, [rbp+57h+var_30]
0x180038179  xor     rcx, rsp; StackCookie
0x18003817c  call    __security_check_cookie
0x180038181  add     rsp, 0D8h
0x180038188  pop     r14
0x18003818a  pop     rdi
0x18003818b  pop     rbx
0x18003818c  pop     rbp
0x18003818d  retn
```
