# I_NetrShareSetInfo

- ea: `0x180029884`
- end: `0x18002a284`
- name: `I_NetrShareSetInfo`
- size: `2560`
- prototype: `__int64 __usercall@<rax>(PCWSTR@<rcx>, PCWSTR SourceString@<rdx>, __int64)`
- caller_count: `2`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002a530`
- `0x18002ae10`

## callees

- `0x180005790`
- `0x180005820`
- `0x180005b80`
- `0x180008930`
- `0x18000a460`
- `0x18000bb10`
- `0x18001deb0`
- `0x18001e80c`
- `0x180020de8`
- `0x180021240`
- `0x180024f2c`
- `0x180026b94`
- `0x180029884`
- `0x18002ae60`
- `0x18002b1dc`
- `0x18002b988`
- `0x18002ba78`
- `0x18002bb88`
- `0x18002bc44`
- `0x18002ef48`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029ee7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029ee7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029abe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029c31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a237`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a241`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a265`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029abe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029c31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a237`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a241`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a265`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a002`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a134`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a002`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a134`
- `ntdll!RtlFreeUnicodeString` at `0x18002a279`
- `ntdll!RtlFreeUnicodeString` at `0x18002a279`
- `ntdll!RtlStringFromGUID` at `0x180029b20`
- `ntdll!RtlStringFromGUID` at `0x180029b20`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18002a05f`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18002a05f`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x180029ded`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x180029ded`
- `ntdll!RtlDeleteSecurityObject` at `0x18002a253`
- `ntdll!RtlDeleteSecurityObject` at `0x18002a253`
- `RPCRT4!RpcImpersonateClient` at `0x18002a15d`
- `RPCRT4!RpcImpersonateClient` at `0x18002a15d`
- `RPCRT4!RpcRevertToSelf` at `0x18002a1a4`
- `RPCRT4!RpcRevertToSelf` at `0x18002a1a4`

## pseudocode

```c
__int64 __fastcall I_NetrShareSetInfo(PCWSTR a1, PCWSTR SourceString, unsigned int a3, __int64 **a4, _DWORD *a5)
{
  __int64 v9; // rdx
  __int64 *v11; // r15
  int v12; // ecx
  unsigned int v13; // edi
  bool v14; // zf
  __int64 v15; // r8
  ULONG v16; // edx
  __int64 *v17; // rax
  int v18; // ecx
  int v19; // edi
  __int64 v20; // rax
  __int64 v21; // r9
  __int64 *v22; // rcx
  unsigned int v23; // eax
  __int64 v24; // rdx
  __int64 *v25; // rcx
  __int64 v26; // rax
  unsigned int v27; // eax
  const WCHAR *v28; // r15
  void *v29; // rax
  unsigned int v30; // edi
  _DWORD *v31; // rax
  _DWORD *v32; // rdx
  __int64 **v33; // rbx
  _DWORD *v34; // rdi
  void *v35; // rdx
  __int64 v36; // rbx
  char v37; // al
  int v38; // r8d
  int v39; // r9d
  _BYTE *v40; // rbx
  PSECURITY_DESCRIPTOR v41; // rax
  ULONG v42; // eax
  ULONG v43; // ecx
  unsigned int v44; // eax
  unsigned int v45; // eax
  __int64 v46; // rdx
  int v47; // r8d
  int v48; // r9d
  __int64 v49; // rbx
  char CurrentThreadId; // al
  int v51; // r8d
  __int64 v52; // r12
  RPC_STATUS v53; // ebx
  unsigned int v54; // eax
  int v55; // eax
  HLOCAL v56; // rbx
  int v57; // [rsp+38h] [rbp-C8h]
  int v58; // [rsp+38h] [rbp-C8h]
  char v59[4]; // [rsp+70h] [rbp-90h] BYREF
  int v60; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v61; // [rsp+78h] [rbp-88h] BYREF
  ULONG SecurityDescriptorLength; // [rsp+80h] [rbp-80h]
  int v63; // [rsp+84h] [rbp-7Ch] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v65; // [rsp+90h] [rbp-70h] BYREF
  int v66; // [rsp+94h] [rbp-6Ch] BYREF
  unsigned int v67; // [rsp+98h] [rbp-68h]
  __int64 *v68; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v69; // [rsp+A8h] [rbp-58h]
  HLOCAL v70; // [rsp+B0h] [rbp-50h]
  int v71; // [rsp+B8h] [rbp-48h] BYREF
  BOOL v72; // [rsp+BCh] [rbp-44h]
  int v73; // [rsp+C0h] [rbp-40h]
  HLOCAL hMem; // [rsp+C8h] [rbp-38h] BYREF
  HLOCAL v75; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v76; // [rsp+D8h] [rbp-28h]
  int v77; // [rsp+E0h] [rbp-20h]
  PCWSTR v78; // [rsp+E8h] [rbp-18h]
  __int64 **v79; // [rsp+F0h] [rbp-10h]
  int *v80; // [rsp+F8h] [rbp-8h]
  __int64 ShareProviderByPath; // [rsp+100h] [rbp+0h]
  struct _UNICODE_STRING GuidString; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v83[16]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v84[76]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int16 v85; // [rsp+1ECh] [rbp+ECh]

  v78 = SourceString;
  v63 = 0;
  v65 = 0;
  v60 = 0;
  v71 = 0;
  SecurityDescriptor = 0;
  v66 = 0;
  hMem = 0;
  GuidString = 0;
  memset_0(v83, 0, 0x78u);
  v59[0] = 0;
  if ( !*a4 )
  {
    if ( a5 )
      *a5 = -1;
    return 87;
  }
  v70 = 0;
  v68 = 0;
  v69 = 0;
  v75 = 0;
  v61 = 0;
  SecurityDescriptorLength = 0;
  v80 = 0;
  v79 = 0;
  if ( a1 )
  {
    if ( (*a1 != 92 || a1[1] != 92 || (a1 += 2) != 0)
      && (!(unsigned __int8)CheckForServerNameEx(a1, v9, v59, 0) || !v59[0]) )
    {
      a1 = 0;
    }
  }
  switch ( a3 )
  {
    case 1u:
      goto LABEL_52;
    case 2u:
LABEL_51:
      v18 = *((_DWORD *)*a4 + 7);
      v69 = (unsigned __int64)&v60;
      v60 = v18;
LABEL_52:
      v11 = (__int64 *)v61;
      v68 = (__int64 *)(*a4)[2];
      goto LABEL_31;
    case 0x1F6u:
    case 0x1F7u:
      if ( a3 == 502 )
      {
        v16 = *((_DWORD *)*a4 + 14);
        v61 = (*a4)[8];
        SecurityDescriptorLength = v16;
      }
      else
      {
        v17 = *a4;
        a1 = (PCWSTR)(*a4)[7];
        v61 = (*a4)[9];
        SecurityDescriptorLength = *((_DWORD *)v17 + 16);
      }
      goto LABEL_51;
  }
  if ( a3 != 505 )
  {
    if ( a3 == 1004 )
    {
      v68 = (__int64 *)**a4;
    }
    else if ( a3 != 1005 )
    {
      if ( a3 != 1006 )
      {
        if ( a3 != 1501 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_cee36e08cc873b175cea1cc8b33051d6_Traceguids, a3);
          }
          if ( a5 )
            *a5 = 0;
          return 124;
        }
        v11 = (__int64 *)(*a4)[1];
        SecurityDescriptorLength = *(_DWORD *)*a4;
        goto LABEL_31;
      }
      v12 = *(_DWORD *)*a4;
      v69 = (unsigned __int64)&v60;
      v60 = v12;
    }
    v11 = 0;
    goto LABEL_31;
  }
  v14 = ((_DWORD)a4[10] & 0x200) == 0;
  v11 = a4[9];
  a1 = (PCWSTR)a4[7];
  SecurityDescriptorLength = *((_DWORD *)a4 + 16);
  v60 = *((_DWORD *)a4 + 7);
  v68 = a4[2];
  v71 = *((_DWORD *)a4 + 23);
  v66 = *((_DWORD *)a4 + 24);
  if ( !v14 )
  {
    v85 = 0;
    if ( RtlStringFromGUID((const GUID *const)((char *)a4 + 100), &GuidString) < 0
      || (int)RtlStringCchPrintfW(v84, 39, L"%ws", GuidString.Buffer) < 0 )
    {
      v13 = 87;
      if ( a5 )
        *a5 = 504;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF__guid_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, v15, (char *)a4 + 100);
      }
      goto LABEL_157;
    }
  }
  v79 = a4;
  v69 = (unsigned __int64)&v60;
  v75 = &v71;
  v80 = &v66;
LABEL_31:
  if ( !SourceString || !*SourceString )
    return 87;
  v13 = ShareEnumCommonEx(2, (int)&hMem, -1, (int)&v63, (__int64)&v61, 0, SourceString, a1, 0, 1, 0, 0, 0);
  if ( v13 )
  {
    if ( hMem )
      LocalFree(hMem);
    return v13;
  }
  if ( v63 )
  {
    v19 = *((_DWORD *)hMem + 2);
    v20 = *((_QWORD *)hMem + 5);
    v73 = v19;
    v76 = v20;
    v72 = (v19 & 0xE000000) != 0;
    v77 = v19 & 0xE000000;
    v67 = ((unsigned int)v19 >> 26) & 1;
    if ( (v19 & 0xE000000) != 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        (unsigned int)WPP_cee36e08cc873b175cea1cc8b33051d6_Traceguids,
        (unsigned int)"I_NetrShareSetInfo",
        v20);
      v20 = v76;
    }
    ShareProviderByPath = SsFindShareProviderByPath(v20);
    if ( v19 < 0 && v11 )
      goto LABEL_64;
    LODWORD(v61) = (unsigned __int8)v19;
    if ( a3 == 1005 && (_BYTE)v19 )
    {
      v13 = 66;
      goto LABEL_156;
    }
    if ( !dword_18005CE2C )
    {
LABEL_80:
      v24 = v69;
      if ( v69 )
      {
        v24 = v69 & -(__int64)(*(_DWORD *)v69 != 0);
        v69 = v24;
      }
      v25 = v68;
      if ( v68 )
      {
        v26 = -1;
        do
          ++v26;
        while ( *((_WORD *)v68 + v26) );
        if ( (unsigned int)v26 > 0x100 )
        {
          if ( a5 )
            *a5 = 4;
          goto LABEL_66;
        }
      }
      else if ( !v24 )
      {
        if ( !v11 )
        {
          if ( a3 != 1005 && a3 != 505 )
          {
            v13 = 0;
            goto LABEL_156;
          }
LABEL_101:
          v28 = v78;
          v83[0] = v78;
          if ( a3 == 505 )
          {
            v33 = v79;
            v13 = CheckShareFlags(a1, v78, v76, (char *)v79 + 84, v72, v67, 0, 1);
            if ( v13 )
              goto LABEL_156;
            LOBYTE(v58) = 1;
            v29 = (void *)CaptureShareInfo(v33, 0, 0, 0, v68, 0, SecurityDescriptor, v58, &v65);
          }
          else
          {
            if ( a3 == 1005 )
            {
              v13 = CheckShareFlags(a1, v78, v76, *a4, v72, v67, 0, 0);
              if ( v13 )
                goto LABEL_156;
              v30 = 4;
              v31 = LocalAlloc(0x40u, 4u);
              v70 = v31;
              v32 = v31;
              if ( v31 )
              {
                *v31 = 0;
                *v31 = *(_DWORD *)*a4;
LABEL_114:
                if ( !v77 || v73 < 0 || (_DWORD)v61 == 1 )
                {
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v49 = *((_QWORD *)WPP_GLOBAL_Control + 2);
                    CurrentThreadId = GetCurrentThreadId();
                    WPP_SF_sdS(v49, 36, v51, (unsigned int)"I_NetrShareSetInfo", CurrentThreadId, (__int64)v28);
                  }
                  v52 = ShareProviderByPath;
                  v53 = RpcImpersonateClient(0);
                  if ( v52 )
                    v54 = (*(__int64 (__fastcall **)(_QWORD, HLOCAL, _QWORD, PCWSTR, const WCHAR *, int, _DWORD *))(v52 + 56))(
                            a3,
                            v70,
                            v30,
                            a1,
                            v28,
                            v60,
                            a5);
                  else
                    v54 = ((__int64 (__fastcall *)(_QWORD, HLOCAL, _QWORD, PCWSTR, const WCHAR *, int, _DWORD *))qword_18005E4F8)(
                            a3,
                            v70,
                            v30,
                            a1,
                            v28,
                            v60,
                            a5);
                  v13 = v54;
                  if ( !v53 )
                    RpcRevertToSelf();
                  if ( !v13 && v73 >= 0 && (v73 & 0x40000000) == 0 )
                  {
                    v75 = 0;
                    v55 = ShareEnumCommonEx(505, (int)&v75, -1, (int)&v63, (__int64)&v61, 0, v28, a1, 0, 0, 0, 0, 0);
                    v56 = v75;
                    if ( !v55 && v63 )
                      SsAddShareToRegistry(v75, *((_QWORD *)v75 + 7), SecurityDescriptor, *((unsigned int *)v75 + 21));
                    if ( v56 )
                      LocalFree(v56);
                  }
                }
                else
                {
                  if ( a3 == 1005 )
                  {
                    v34 = v32;
                  }
                  else
                  {
                    v34 = 0;
                    if ( a3 == 505 )
                      v34 = v32 + 21;
                  }
                  v35 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v36 = *((_QWORD *)WPP_GLOBAL_Control + 2);
                    v37 = GetCurrentThreadId();
                    WPP_SF_sdSSd(v36, v66, v38, v39, v37, (__int64)v28, (__int64)v84, v66);
                    v35 = WPP_GLOBAL_Control;
                  }
                  if ( a3 != 505 || (v40 = v84, ((_DWORD)v79[10] & 0x200) == 0) )
                    v40 = 0;
                  v41 = SecurityDescriptor;
                  if ( SecurityDescriptor )
                  {
                    v42 = RtlLengthSecurityDescriptor(SecurityDescriptor);
                    v35 = WPP_GLOBAL_Control;
                    v43 = v42;
                    v41 = SecurityDescriptor;
                  }
                  else
                  {
                    v43 = 0;
                  }
                  if ( qword_18005E590 )
                  {
                    v44 = ((__int64 (__fastcall *)(_QWORD, const WCHAR *, PCWSTR, __int64 *, unsigned __int64, PSECURITY_DESCRIPTOR, ULONG, _DWORD *, HLOCAL, int *, _BYTE *))qword_18005E590)(
                            v67,
                            v28,
                            a1,
                            v68,
                            v69,
                            v41,
                            v43,
                            v34,
                            v75,
                            v80,
                            v40);
                    v35 = WPP_GLOBAL_Control;
                  }
                  else
                  {
                    v44 = 1;
                  }
                  v45 = RemapClusterErrorCode(v44, v35);
                  v13 = v45;
                  if ( v45
                    && (_UNKNOWN **)v46 != &WPP_GLOBAL_Control
                    && (*(_BYTE *)(v46 + 28) & 4) != 0
                    && *(_BYTE *)(v46 + 25) )
                  {
                    WPP_SF_sSd(*(_QWORD *)(v46 + 16), v46, v47, v48, (__int64)v28, v45);
                  }
                }
                goto LABEL_156;
              }
LABEL_106:
              if ( a5 )
                *a5 = 0;
              v13 = 8;
              goto LABEL_156;
            }
            LOBYTE(v57) = 1;
            v29 = (void *)CaptureShareInfo(v83, 0, 0, 0, v25, 0, SecurityDescriptor, v57, &v65);
            a3 = 503;
          }
          v70 = v29;
          v32 = v29;
          if ( v29 )
          {
            v30 = v65;
            goto LABEL_114;
          }
          goto LABEL_106;
        }
LABEL_94:
        if ( RtlValidRelativeSecurityDescriptor(v11, SecurityDescriptorLength, 0) )
        {
          v27 = ShareAssignSecurityDescriptor(v11, &SecurityDescriptor);
          if ( !v27 )
          {
            v25 = v68;
            goto LABEL_101;
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_cee36e08cc873b175cea1cc8b33051d6_Traceguids, v27);
          }
        }
LABEL_64:
        if ( a5 )
          *a5 = 501;
LABEL_66:
        v13 = 87;
LABEL_156:
        LocalFree(hMem);
LABEL_157:
        if ( SecurityDescriptor )
          RtlDeleteSecurityObject(&SecurityDescriptor);
        if ( v70 )
          LocalFree(v70);
        if ( GuidString.Buffer )
          RtlFreeUnicodeString(&GuidString);
        return v13;
      }
      if ( !v11 )
        goto LABEL_101;
      goto LABEL_94;
    }
    if ( v19 >= 0 )
    {
      if ( (unsigned __int8)v19 == 1 )
      {
        v22 = (__int64 *)&SsSharePrintSecurityObject;
      }
      else
      {
        if ( dword_18005CDA4 )
        {
          v23 = SsCheckAccessForShareChange(v78, v76, 0, v21);
          goto LABEL_79;
        }
        v22 = SsShareFileSecurityObject;
      }
    }
    else
    {
      v22 = SsShareAdminSecurityObject;
    }
    v23 = SsCheckAccess(v22, v78, 16, v21);
LABEL_79:
    v13 = v23;
    if ( v23 )
      goto LABEL_156;
    goto LABEL_80;
  }
  if ( hMem )
    LocalFree(hMem);
  return 2310;
}

```

## disassembly

```asm
0x180029884  push    rbp
0x180029886  push    rbx
0x180029887  push    rsi
0x180029888  push    rdi
0x180029889  push    r12
0x18002988b  push    r13
0x18002988d  push    r14
0x18002988f  push    r15
0x180029891  lea     rbp, [rsp-108h]
0x180029899  sub     rsp, 208h
0x1800298a0  mov     rax, cs:__security_cookie
0x1800298a7  xor     rax, rsp
0x1800298aa  mov     [rbp+140h+var_50], rax
0x1800298b1  mov     rsi, [rbp+140h+arg_20]
0x1800298b8  xor     r12d, r12d
0x1800298bb  mov     r13d, r8d
0x1800298be  mov     [rbp+140h+var_158], rdx
0x1800298c2  mov     rdi, rdx
0x1800298c5  mov     [rbp+140h+var_1BC], r12d
0x1800298c9  mov     r14, rcx
0x1800298cc  mov     [rbp+140h+var_1B0], r12d
0x1800298d0  xorps   xmm0, xmm0
0x1800298d3  mov     [rsp+240h+var_1CC], r12d
0x1800298d8  lea     r8d, [r12+78h]; Size
0x1800298dd  mov     [rbp+140h+var_188], r12d
0x1800298e1  xor     edx, edx; Val
0x1800298e3  mov     [rbp+140h+SecurityDescriptor], r12
0x1800298e7  lea     rcx, [rbp+140h+var_120]; void *
0x1800298eb  mov     [rbp+140h+var_1AC], r12d
0x1800298ef  mov     rbx, r9
0x1800298f2  mov     [rbp+140h+hMem], r12
0x1800298f6  movups  xmmword ptr [rbp+140h+GuidString.Length], xmm0
0x1800298fa  call    memset_0
0x1800298ff  mov     [rsp+240h+var_1D0], r12b
0x180029904  cmp     [rbx], r12
0x180029907  jnz     short loc_18002993C
0x180029909  test    rsi, rsi
0x18002990c  jz      short loc_180029914
0x18002990e  mov     dword ptr [rsi], 0FFFFFFFFh
0x180029914  mov     eax, 57h ; 'W'
0x180029919  mov     rcx, [rbp+140h+var_50]
0x180029920  xor     rcx, rsp; StackCookie
0x180029923  call    __security_check_cookie
0x180029928  add     rsp, 208h
0x18002992f  pop     r15
0x180029931  pop     r14
0x180029933  pop     r13
0x180029935  pop     r12
0x180029937  pop     rdi
0x180029938  pop     rsi
0x180029939  pop     rbx
0x18002993a  pop     rbp
0x18002993b  retn
0x18002993c  mov     [rbp+140h+var_190], r12
0x180029940  mov     [rbp+140h+var_1A0], r12
0x180029944  mov     [rbp+140h+var_198], r12
0x180029948  mov     [rbp+140h+var_170], r12
0x18002994c  mov     [rsp+240h+var_1C8], r12
0x180029951  mov     [rbp+140h+SecurityDescriptorLength], r12d
0x180029955  mov     [rbp+140h+var_148], r12
0x180029959  mov     [rbp+140h+var_150], r12
0x18002995d  test    r14, r14
0x180029960  jz      short loc_180029995
0x180029962  cmp     word ptr [r14], 5Ch ; '\'
0x180029967  jnz     short loc_180029977
0x180029969  cmp     word ptr [r14+2], 5Ch ; '\'
0x18002996f  jnz     short loc_180029977
0x180029971  add     r14, 4
0x180029975  jz      short loc_180029995
0x180029977  xor     r9d, r9d
0x18002997a  lea     r8, [rsp+240h+var_1D0]
0x18002997f  mov     rcx, r14
0x180029982  call    CheckForServerNameEx
0x180029987  test    al, al
0x180029989  jz      short loc_180029992
0x18002998b  cmp     [rsp+240h+var_1D0], r12b
0x180029990  jnz     short loc_180029995
0x180029992  mov     r14, r12
0x180029995  mov     eax, r13d
0x180029998  sub     eax, 1
0x18002999b  jz      loc_180029C0D
0x1800299a1  sub     eax, 1
0x1800299a4  jz      loc_180029BFA
0x1800299aa  sub     eax, 1F4h
0x1800299af  jz      loc_180029BBE
0x1800299b5  sub     eax, 1
0x1800299b8  jz      loc_180029BBE
0x1800299be  sub     eax, 2
0x1800299c1  jz      loc_180029ADA
0x1800299c7  sub     eax, 1F3h
0x1800299cc  jz      loc_180029ACB
0x1800299d2  sub     eax, 1
0x1800299d5  jz      short loc_180029A4D
0x1800299d7  sub     eax, 1
0x1800299da  jz      short loc_180029A3B
0x1800299dc  cmp     eax, 1EFh
0x1800299e1  jz      short loc_180029A2D
0x1800299e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800299ea  lea     r12, WPP_GLOBAL_Control
0x1800299f1  cmp     rcx, r12
0x1800299f4  jz      short loc_180029A1A
0x1800299f6  test    byte ptr [rcx+1Ch], 4
0x1800299fa  jz      short loc_180029A1A
0x1800299fc  cmp     byte ptr [rcx+19h], 1
0x180029a00  jb      short loc_180029A1A
0x180029a02  mov     rcx, [rcx+10h]
0x180029a06  lea     r8, WPP_cee36e08cc873b175cea1cc8b33051d6_Traceguids
0x180029a0d  mov     edx, 21h ; '!'
0x180029a12  mov     r9d, r13d
0x180029a15  call    WPP_SF_d
0x180029a1a  xor     ecx, ecx
0x180029a1c  test    rsi, rsi
0x180029a1f  jz      short loc_180029A23
0x180029a21  mov     [rsi], ecx
0x180029a23  mov     eax, 7Ch ; '|'
0x180029a28  jmp     loc_180029919
0x180029a2d  mov     rax, [rbx]
0x180029a30  mov     ecx, [rax]
0x180029a32  mov     r15, [rax+8]
0x180029a36  mov     [rbp+140h+SecurityDescriptorLength], ecx
0x180029a39  jmp     short loc_180029A50
0x180029a3b  mov     rax, [rbx]
0x180029a3e  mov     ecx, [rax]
0x180029a40  lea     rax, [rsp+240h+var_1CC]
0x180029a45  mov     [rbp+140h+var_198], rax
0x180029a49  mov     [rsp+240h+var_1CC], ecx
0x180029a4d  mov     r15, r12
0x180029a50  test    rdi, rdi
0x180029a53  jz      loc_180029914
0x180029a59  cmp     [rdi], r12w
0x180029a5d  jz      loc_180029914
0x180029a63  mov     [rsp+240h+var_1E0], r12d; int
0x180029a68  lea     rax, [rsp+240h+var_1C8]
0x180029a6d  mov     [rsp+240h+var_1E8], r12b; char
0x180029a72  lea     r9, [rbp+140h+var_1BC]; int
0x180029a76  mov     [rsp+240h+var_1F0], r12b; char
0x180029a7b  lea     rdx, [rbp+140h+hMem]; int
0x180029a7f  mov     [rsp+240h+var_1F8], 1; char
0x180029a84  or      r8d, 0FFFFFFFFh; int
0x180029a88  mov     [rsp+240h+var_200], r12b; char
0x180029a8d  mov     ecx, 2; int
0x180029a92  mov     [rsp+240h+var_208], r14; PCWSTR
0x180029a97  mov     [rsp+240h+SourceString], rdi; SourceString
0x180029a9c  mov     [rsp+240h+var_218], r12; __int64
0x180029aa1  mov     [rsp+240h+var_220], rax; __int64
0x180029aa6  call    ShareEnumCommonEx
0x180029aab  mov     edi, eax
0x180029aad  test    eax, eax
0x180029aaf  jz      loc_180029C22
0x180029ab5  mov     rcx, [rbp+140h+hMem]; hMem
0x180029ab9  test    rcx, rcx
0x180029abc  jz      short loc_180029AC4
0x180029abe  call    cs:__imp_LocalFree
0x180029ac4  mov     eax, edi
0x180029ac6  jmp     loc_180029919
0x180029acb  mov     rax, [rbx]
0x180029ace  mov     rcx, [rax]
0x180029ad1  mov     [rbp+140h+var_1A0], rcx
0x180029ad5  jmp     loc_180029A4D
0x180029ada  test    dword ptr [rbx+50h], 200h
0x180029ae1  mov     eax, [rbx+40h]
0x180029ae4  mov     r15, [rbx+48h]
0x180029ae8  mov     r14, [rbx+38h]
0x180029aec  mov     [rbp+140h+SecurityDescriptorLength], eax
0x180029aef  mov     eax, [rbx+1Ch]
0x180029af2  mov     [rsp+240h+var_1CC], eax
0x180029af6  mov     rax, [rbx+10h]
0x180029afa  mov     [rbp+140h+var_1A0], rax
0x180029afe  mov     eax, [rbx+5Ch]
0x180029b01  mov     [rbp+140h+var_188], eax
0x180029b04  mov     eax, [rbx+60h]
0x180029b07  mov     [rbp+140h+var_1AC], eax
0x180029b0a  jz      loc_180029B9C
0x180029b10  lea     rdx, [rbp+140h+GuidString]; GuidString
0x180029b14  mov     [rbp+140h+var_54], r12w
0x180029b1c  lea     rcx, [rbx+64h]; Guid
0x180029b20  call    cs:__imp_RtlStringFromGUID
0x180029b26  test    eax, eax
0x180029b28  js      short loc_180029B4A
0x180029b2a  mov     r9, [rbp+140h+GuidString.Buffer]
0x180029b2e  lea     r8, aWs; "%ws"
0x180029b35  mov     edx, 27h ; '''
0x180029b3a  lea     rcx, [rbp+140h+var_A0]
0x180029b41  call    RtlStringCchPrintfW
0x180029b46  test    eax, eax
0x180029b48  jns     short loc_180029B9C
0x180029b4a  mov     edi, 57h ; 'W'
0x180029b4f  test    rsi, rsi
0x180029b52  jz      short loc_180029B5A
0x180029b54  mov     dword ptr [rsi], 1F8h
0x180029b5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180029b61  lea     r12, WPP_GLOBAL_Control
0x180029b68  cmp     rcx, r12
0x180029b6b  jz      loc_18002A247
0x180029b71  test    byte ptr [rcx+1Ch], 4
0x180029b75  jz      loc_18002A247
0x180029b7b  cmp     byte ptr [rcx+19h], 1
0x180029b7f  jb      loc_18002A247
0x180029b85  mov     rcx, [rcx+10h]
0x180029b89  lea     r9, [rbx+64h]
0x180029b8d  mov     edx, 20h ; ' '
0x180029b92  call    WPP_SF__guid_d
0x180029b97  jmp     loc_18002A247
0x180029b9c  lea     rax, [rsp+240h+var_1CC]
0x180029ba1  mov     [rbp+140h+var_150], rbx
0x180029ba5  mov     [rbp+140h+var_198], rax
0x180029ba9  lea     rax, [rbp+140h+var_188]
0x180029bad  mov     [rbp+140h+var_170], rax
0x180029bb1  lea     rax, [rbp+140h+var_1AC]
0x180029bb5  mov     [rbp+140h+var_148], rax
0x180029bb9  jmp     loc_180029A50
0x180029bbe  cmp     r13d, 1F6h
0x180029bc5  jnz     short loc_180029BDB
0x180029bc7  mov     rax, [rbx]
0x180029bca  mov     rcx, [rax+40h]
0x180029bce  mov     edx, [rax+38h]
0x180029bd1  mov     [rsp+240h+var_1C8], rcx
0x180029bd6  mov     [rbp+140h+SecurityDescriptorLength], edx
0x180029bd9  jmp     short loc_180029BFA
0x180029bdb  cmp     r13d, 1F7h
0x180029be2  jnz     short loc_180029BFA
0x180029be4  mov     rax, [rbx]
0x180029be7  mov     rcx, [rax+48h]
0x180029beb  mov     r14, [rax+38h]
0x180029bef  mov     [rsp+240h+var_1C8], rcx
0x180029bf4  mov     ecx, [rax+40h]
0x180029bf7  mov     [rbp+140h+SecurityDescriptorLength], ecx
0x180029bfa  mov     rax, [rbx]
0x180029bfd  mov     ecx, [rax+1Ch]
0x180029c00  lea     rax, [rsp+240h+var_1CC]
0x180029c05  mov     [rbp+140h+var_198], rax
0x180029c09  mov     [rsp+240h+var_1CC], ecx
0x180029c0d  mov     rax, [rbx]
0x180029c10  mov     r15, [rsp+240h+var_1C8]
0x180029c15  mov     rax, [rax+10h]
0x180029c19  mov     [rbp+140h+var_1A0], rax
0x180029c1d  jmp     loc_180029A50
0x180029c22  cmp     [rbp+140h+var_1BC], r12d
0x180029c26  jnz     short loc_180029C41
0x180029c28  mov     rcx, [rbp+140h+hMem]; hMem
0x180029c2c  test    rcx, rcx
0x180029c2f  jz      short loc_180029C37
0x180029c31  call    cs:__imp_LocalFree
0x180029c37  mov     eax, 906h
0x180029c3c  jmp     loc_180029919
0x180029c41  mov     rax, [rbp+140h+hMem]
0x180029c45  mov     ecx, r12d
0x180029c48  lea     r12, WPP_GLOBAL_Control
0x180029c4f  mov     edi, [rax+8]
0x180029c52  mov     edx, edi
0x180029c54  mov     rax, [rax+28h]
0x180029c58  and     edx, 0E000000h
0x180029c5e  mov     [rbp+140h+var_180], edi
0x180029c61  setnz   cl
0x180029c64  mov     [rbp+140h+var_168], rax
0x180029c68  mov     [rbp+140h+var_184], ecx
0x180029c6b  mov     ecx, edi
0x180029c6d  shr     ecx, 1Ah
0x180029c70  and     ecx, 1
0x180029c73  mov     [rbp+140h+var_160], edx
0x180029c76  mov     [rbp+140h+var_1A8], ecx
0x180029c79  test    edx, edx
0x180029c7b  jz      short loc_180029CBA
0x180029c7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029c84  cmp     rcx, r12
0x180029c87  jz      short loc_180029CBA
0x180029c89  test    byte ptr [rcx+1Ch], 4
0x180029c8d  jz      short loc_180029CBA
0x180029c8f  cmp     byte ptr [rcx+19h], 2
0x180029c93  jb      short loc_180029CBA
0x180029c95  mov     rcx, [rcx+10h]
0x180029c99  lea     r9, aINetrshareseti; "I_NetrShareSetInfo"
0x180029ca0  mov     edx, 22h ; '"'
0x180029ca5  mov     [rsp+240h+var_220], rax
0x180029caa  lea     r8, WPP_cee36e08cc873b175cea1cc8b33051d6_Traceguids
0x180029cb1  call    WPP_SF_sS
0x180029cb6  mov     rax, [rbp+140h+var_168]
0x180029cba  mov     rcx, rax
0x180029cbd  call    SsFindShareProviderByPath
0x180029cc2  xor     r8d, r8d
0x180029cc5  mov     [rbp+140h+var_140], rax
0x180029cc9  test    edi, edi
0x180029ccb  jns     short loc_180029CE7
0x180029ccd  test    r15, r15
0x180029cd0  jz      short loc_180029CE7
0x180029cd2  test    rsi, rsi
0x180029cd5  jz      short loc_180029CDD
0x180029cd7  mov     dword ptr [rsi], 1F5h
0x180029cdd  mov     edi, 57h ; 'W'
0x180029ce2  jmp     loc_18002A23D
0x180029ce7  movzx   eax, dil
0x180029ceb  mov     dword ptr [rsp+240h+var_1C8], eax
0x180029cef  cmp     r13d, 3EDh
0x180029cf6  jnz     short loc_180029D07
0x180029cf8  test    dil, dil
0x180029cfb  jz      short loc_180029D07
0x180029cfd  mov     edi, 42h ; 'B'
0x180029d02  jmp     loc_18002A23D
0x180029d07  cmp     cs:dword_18005CE2C, r8d
0x180029d0e  jz      short loc_180029D66
  ... truncated ...
```
