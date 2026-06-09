# CapabilityUtils::CheckForPackageInPrivilegedList(ushort const *,ushort const *,bool *)

- ea: `0x1802deedc`
- end: `0x1802df1ac`
- name: `?CheckForPackageInPrivilegedList@CapabilityUtils@@YAJPEBG0PEA_N@Z`
- size: `720`
- prototype: `__int64 __fastcall(LPCWSTR StringSid, const unsigned __int16 *, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801124dc`

## callees

- `0x18013f43c`
- `0x18013f4a4`
- `0x1802deedc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802df0cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802df0cb`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1802df131`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1802df131`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1802df13f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1802df16d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1802df177`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1802df13f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1802df16d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1802df177`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1802df10c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1802df10c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1802df0c1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1802df0c1`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1802defdc`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1802df184`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1802defdc`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1802df184`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x1802defa7`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x1802df06d`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x1802defa7`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x1802df06d`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x1802df11d`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x1802df11d`

## pseudocode

```c
__int64 __fastcall CapabilityUtils::CheckForPackageInPrivilegedList(
        LPCWSTR StringSid,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        bool *a4)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  __int64 v5; // r9
  __int64 v9; // rdi
  signed int ObjectProperties; // ebx
  __int64 v11; // rdx
  const WCHAR *v12; // rdi
  unsigned int v13; // esi
  signed int LastError; // eax
  char v15; // dl
  BOOL v16; // eax
  PSID v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  PSID pSid1; // [rsp+40h] [rbp-10h] BYREF
  PSID Sid; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v23; // [rsp+90h] [rbp+40h] BYREF
  __int64 v24; // [rsp+98h] [rbp+48h] BYREF

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v5 = (unsigned int)tls_index;
  v23 = 0;
  *(_BYTE *)a3 = 0;
  v9 = ThreadLocalStoragePointer[v5];
  v24 = 0;
  if ( dword_1804B7424 > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&dword_1804B7424);
    if ( dword_1804B7424 == -1 )
    {
      *(DEVPROPKEY *)byte_1804B6140 = DEVPKEY_DeviceContainer_CustomPrivilegedPackageFamilyNames;
      dword_1804B6154 = 0;
      qword_1804B6158 = 0;
      Init_thread_footer(&dword_1804B7424);
    }
  }
  ObjectProperties = DevGetObjectProperties(2, a2, 0, 1, byte_1804B6140, &v23, &v24);
  if ( ObjectProperties >= 0 )
  {
    v11 = v24;
    if ( v23 != 1 || *(_DWORD *)(v24 + 32) != 8210 || !*(_DWORD *)(v24 + 36) || !*(_QWORD *)(v24 + 40) )
    {
      DevFreeObjectProperties(v23, v24);
      v23 = 0;
      if ( dword_1804B7428 > *(_DWORD *)(v9 + 4) )
      {
        Init_thread_header(&dword_1804B7428);
        if ( dword_1804B7428 == -1 )
        {
          *(DEVPROPKEY *)byte_1804B6160 = DEVPKEY_DeviceContainer_PrivilegedPackageFamilyNames;
          dword_1804B6174 = 0;
          qword_1804B6178 = 0;
          Init_thread_footer(&dword_1804B7428);
        }
      }
      ObjectProperties = DevGetObjectProperties(2, a2, 0, 1, byte_1804B6160, &v23, &v24);
      if ( ObjectProperties < 0 )
      {
LABEL_35:
        v11 = v24;
LABEL_36:
        DevFreeObjectProperties(v23, v11);
        return (unsigned int)ObjectProperties;
      }
      v11 = v24;
      if ( v23 != 1 || *(_DWORD *)(v24 + 32) != 8210 || !*(_DWORD *)(v24 + 36) || !*(_QWORD *)(v24 + 40) )
      {
        ObjectProperties = -2147418113;
        goto LABEL_36;
      }
    }
    v12 = *(const WCHAR **)(v11 + 40);
    v13 = *(_DWORD *)(v11 + 36);
    ObjectProperties = 0;
    Sid = 0;
    if ( ConvertStringSidToSidW(StringSid, &Sid) )
      goto LABEL_21;
    LastError = GetLastError();
    ObjectProperties = LastError;
    if ( LastError > 0 )
      ObjectProperties = (unsigned __int16)LastError | 0x80070000;
    if ( ObjectProperties >= 0 )
    {
LABEL_21:
      v15 = 1;
      while ( v13 >= 2 && *v12 )
      {
        pSid1 = 0;
        if ( v15 == 1 && !lstrcmpiW(v12, L"*") )
        {
          *(_BYTE *)a3 = 1;
          break;
        }
        ObjectProperties = AppContainerDeriveSidFromMoniker(v12, &pSid1);
        if ( ObjectProperties >= 0 )
        {
          v16 = EqualSid(pSid1, Sid);
          v17 = pSid1;
          if ( v16 )
          {
            *(_BYTE *)a3 = 1;
            FreeSid(v17);
            break;
          }
          FreeSid(pSid1);
        }
        v15 = 0;
        v18 = -1;
        do
          ++v18;
        while ( v12[v18] );
        v19 = (unsigned int)(v18 + 1);
        v12 += v19;
        v13 += -2 * v19;
      }
      FreeSid(Sid);
    }
    goto LABEL_35;
  }
  return (unsigned int)ObjectProperties;
}

```

## disassembly

```asm
0x1802deedc  mov     [rsp-28h+arg_0], rbx
0x1802deee1  mov     [rsp-28h+arg_8], rsi
0x1802deee6  push    rbp
0x1802deee7  push    rdi
0x1802deee8  push    r12
0x1802deeea  push    r14
0x1802deeec  push    r15
0x1802deeee  mov     rbp, rsp
0x1802deef1  sub     rsp, 50h
0x1802deef5  mov     rax, gs:58h
0x1802deefe  xor     r12d, r12d
0x1802def01  mov     r9d, cs:_tls_index
0x1802def08  mov     r15, rcx
0x1802def0b  mov     ecx, 4
0x1802def10  mov     r14, r8
0x1802def13  mov     rsi, rdx
0x1802def16  mov     [rbp+arg_10], r12d
0x1802def1a  mov     [r8], r12b
0x1802def1d  mov     rdi, [rax+r9*8]
0x1802def21  mov     [rbp+arg_18], r12
0x1802def25  mov     eax, [rdi+rcx]
0x1802def28  cmp     cs:dword_1804B7424, eax
0x1802def2e  jle     short loc_1802DEF79
0x1802def30  lea     rcx, dword_1804B7424
0x1802def37  call    _Init_thread_header
0x1802def3c  cmp     cs:dword_1804B7424, 0FFFFFFFFh
0x1802def43  jnz     short loc_1802DEF79
0x1802def45  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceContainer_CustomPrivilegedPackageFamilyNames.fmtid.Data1
0x1802def4c  mov     eax, cs:DEVPKEY_DeviceContainer_CustomPrivilegedPackageFamilyNames.pid
0x1802def52  lea     rcx, dword_1804B7424
0x1802def59  mov     dword ptr cs:byte_1804B6140+10h, eax
0x1802def5f  movups  xmmword ptr cs:byte_1804B6140, xmm0
0x1802def66  mov     cs:dword_1804B6154, r12d
0x1802def6d  mov     cs:qword_1804B6158, r12
0x1802def74  call    _Init_thread_footer
0x1802def79  lea     rax, [rbp+arg_18]
0x1802def7d  mov     r9d, 1
0x1802def83  mov     [rsp+50h+var_20], rax
0x1802def88  xor     r8d, r8d
0x1802def8b  lea     rax, [rbp+arg_10]
0x1802def8f  mov     rdx, rsi
0x1802def92  mov     [rsp+50h+var_28], rax
0x1802def97  lea     rax, byte_1804B6140
0x1802def9e  lea     ecx, [r9+1]
0x1802defa2  mov     [rsp+50h+var_30], rax
0x1802defa7  call    cs:__imp_DevGetObjectProperties
0x1802defad  mov     ebx, eax
0x1802defaf  test    eax, eax
0x1802defb1  js      loc_1802DF18A
0x1802defb7  mov     ecx, [rbp+arg_10]
0x1802defba  mov     rdx, [rbp+arg_18]
0x1802defbe  cmp     ecx, 1
0x1802defc1  jnz     short loc_1802DEFDC
0x1802defc3  cmp     dword ptr [rdx+20h], 2012h
0x1802defca  jnz     short loc_1802DEFDC
0x1802defcc  cmp     [rdx+24h], r12d
0x1802defd0  jbe     short loc_1802DEFDC
0x1802defd2  cmp     [rdx+28h], r12
0x1802defd6  jnz     loc_1802DF0AC
0x1802defdc  call    cs:__imp_DevFreeObjectProperties
0x1802defe2  mov     eax, 4
0x1802defe7  mov     [rbp+arg_10], r12d
0x1802defeb  mov     eax, [rdi+rax]
0x1802defee  cmp     cs:dword_1804B7428, eax
0x1802deff4  jle     short loc_1802DF03F
0x1802deff6  lea     rcx, dword_1804B7428
0x1802deffd  call    _Init_thread_header
0x1802df002  cmp     cs:dword_1804B7428, 0FFFFFFFFh
0x1802df009  jnz     short loc_1802DF03F
0x1802df00b  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceContainer_PrivilegedPackageFamilyNames.fmtid.Data1
0x1802df012  mov     eax, cs:DEVPKEY_DeviceContainer_PrivilegedPackageFamilyNames.pid
0x1802df018  lea     rcx, dword_1804B7428
0x1802df01f  mov     dword ptr cs:byte_1804B6160+10h, eax
0x1802df025  movups  xmmword ptr cs:byte_1804B6160, xmm0
0x1802df02c  mov     cs:dword_1804B6174, r12d
0x1802df033  mov     cs:qword_1804B6178, r12
0x1802df03a  call    _Init_thread_footer
0x1802df03f  lea     rax, [rbp+arg_18]
0x1802df043  mov     r9d, 1
0x1802df049  mov     [rsp+50h+var_20], rax
0x1802df04e  xor     r8d, r8d
0x1802df051  lea     rax, [rbp+arg_10]
0x1802df055  mov     rdx, rsi
0x1802df058  mov     [rsp+50h+var_28], rax
0x1802df05d  lea     rax, byte_1804B6160
0x1802df064  lea     ecx, [r9+1]
0x1802df068  mov     [rsp+50h+var_30], rax
0x1802df06d  call    cs:__imp_DevGetObjectProperties
0x1802df073  mov     ebx, eax
0x1802df075  test    eax, eax
0x1802df077  js      loc_1802DF17D
0x1802df07d  cmp     [rbp+arg_10], 1
0x1802df081  mov     rdx, [rbp+arg_18]
0x1802df085  jnz     loc_1802DF1A5
0x1802df08b  cmp     dword ptr [rdx+20h], 2012h
0x1802df092  jnz     loc_1802DF1A5
0x1802df098  cmp     [rdx+24h], r12d
0x1802df09c  jbe     loc_1802DF1A5
0x1802df0a2  cmp     [rdx+28h], r12
0x1802df0a6  jz      loc_1802DF1A5
0x1802df0ac  mov     rdi, [rdx+28h]
0x1802df0b0  mov     rcx, r15; StringSid
0x1802df0b3  mov     esi, [rdx+24h]
0x1802df0b6  mov     ebx, r12d
0x1802df0b9  lea     rdx, [rbp+Sid]; Sid
0x1802df0bd  mov     [rbp+Sid], r12
0x1802df0c1  call    cs:__imp_ConvertStringSidToSidW
0x1802df0c7  test    eax, eax
0x1802df0c9  jnz     short loc_1802DF0E8
0x1802df0cb  call    cs:__imp_GetLastError
0x1802df0d1  mov     ebx, eax
0x1802df0d3  test    eax, eax
0x1802df0d5  jle     short loc_1802DF0E0
0x1802df0d7  movzx   ebx, ax
0x1802df0da  or      ebx, 80070000h
0x1802df0e0  test    ebx, ebx
0x1802df0e2  js      loc_1802DF17D
0x1802df0e8  mov     dl, 1
0x1802df0ea  cmp     esi, 2
0x1802df0ed  jb      loc_1802DF173
0x1802df0f3  cmp     [rdi], r12w
0x1802df0f7  jz      short loc_1802DF173
0x1802df0f9  mov     [rbp+pSid1], r12
0x1802df0fd  cmp     dl, 1
0x1802df100  jnz     short loc_1802DF116
0x1802df102  lea     rdx, asc_1803FC80C; "*"
0x1802df109  mov     rcx, rdi; lpString1
0x1802df10c  call    cs:__imp_lstrcmpiW
0x1802df112  test    eax, eax
0x1802df114  jz      short loc_1802DF163
0x1802df116  lea     rdx, [rbp+pSid1]
0x1802df11a  mov     rcx, rdi
0x1802df11d  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x1802df123  mov     ebx, eax
0x1802df125  test    eax, eax
0x1802df127  js      short loc_1802DF145
0x1802df129  mov     rdx, [rbp+Sid]; pSid2
0x1802df12d  mov     rcx, [rbp+pSid1]; pSid1
0x1802df131  call    cs:__imp_EqualSid
0x1802df137  mov     rcx, [rbp+pSid1]; pSid
0x1802df13b  test    eax, eax
0x1802df13d  jnz     short loc_1802DF169
0x1802df13f  call    cs:__imp_FreeSid
0x1802df145  mov     dl, r12b
0x1802df148  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1802df14c  inc     rcx
0x1802df14f  cmp     [rdi+rcx*2], r12w
0x1802df154  jnz     short loc_1802DF14C
0x1802df156  inc     ecx
0x1802df158  imul    eax, ecx, -2
0x1802df15b  lea     rdi, [rdi+rcx*2]
0x1802df15f  add     esi, eax
0x1802df161  jmp     short loc_1802DF0EA
0x1802df163  mov     byte ptr [r14], 1
0x1802df167  jmp     short loc_1802DF173
0x1802df169  mov     byte ptr [r14], 1
0x1802df16d  call    cs:__imp_FreeSid
0x1802df173  mov     rcx, [rbp+Sid]; pSid
0x1802df177  call    cs:__imp_FreeSid
0x1802df17d  mov     rdx, [rbp+arg_18]
0x1802df181  mov     ecx, [rbp+arg_10]
0x1802df184  call    cs:__imp_DevFreeObjectProperties
0x1802df18a  lea     r11, [rsp+50h+var_s0]
0x1802df18f  mov     eax, ebx
0x1802df191  mov     rbx, [r11+30h]
0x1802df195  mov     rsi, [r11+38h]
0x1802df199  mov     rsp, r11
0x1802df19c  pop     r15
0x1802df19e  pop     r14
0x1802df1a0  pop     r12
0x1802df1a2  pop     rdi
0x1802df1a3  pop     rbp
0x1802df1a4  retn
0x1802df1a5  mov     ebx, 8000FFFFh
0x1802df1aa  jmp     short loc_1802DF181
```
