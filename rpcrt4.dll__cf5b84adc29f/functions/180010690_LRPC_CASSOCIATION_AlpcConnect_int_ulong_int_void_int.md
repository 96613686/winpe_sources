# LRPC_CASSOCIATION::AlpcConnect(int,ulong,int,void *,int *)

- ea: `0x180010690`
- end: `0x180010e41`
- name: `?AlpcConnect@LRPC_CASSOCIATION@@AEAAJHKHPEAXPEAH@Z`
- size: `1969`
- prototype: `__int64 __fastcall(LRPC_CASSOCIATION *this, int, unsigned int, int, void *, int *)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002aa3c`
- `0x1800bd310`

## callees

- `0x180010690`
- `0x180010f10`
- `0x180011000`
- `0x180011118`
- `0x180022e80`
- `0x180023020`
- `0x180023a40`
- `0x180028670`
- `0x1800295d8`
- `0x18002e750`
- `0x180036048`
- `0x1800361a0`
- `0x1800a8378`
- `0x1800ceca9`
- `0x1800ceda0`
- `0x1800d7010`

## import_xrefs

- `ntdll!NtAlpcConnectPortEx` at `0x180010a48`
- `ntdll!NtAlpcConnectPortEx` at `0x180010a48`
- `ntdll!NtAlpcConnectPort` at `0x1800108e8`
- `ntdll!NtAlpcConnectPort` at `0x1800108e8`
- `ntdll!wcsstr` at `0x18001073e`
- `ntdll!wcsstr` at `0x18001073e`
- `ntdll!RtlGetAppContainerNamedObjectPath` at `0x18001075e`
- `ntdll!RtlGetAppContainerNamedObjectPath` at `0x18001075e`
- `ntdll!RtlFreeUnicodeString` at `0x180010b15`
- `ntdll!RtlFreeUnicodeString` at `0x180010b15`
- `ntdll!RtlLeaveCriticalSection` at `0x180010b5d`
- `ntdll!RtlLeaveCriticalSection` at `0x180010bd0`
- `ntdll!RtlLeaveCriticalSection` at `0x180010bf1`
- `ntdll!RtlLeaveCriticalSection` at `0x180010d27`
- `ntdll!RtlLeaveCriticalSection` at `0x180010d92`
- `ntdll!RtlLeaveCriticalSection` at `0x180010db2`
- `ntdll!RtlLeaveCriticalSection` at `0x180010b5d`
- `ntdll!RtlLeaveCriticalSection` at `0x180010bd0`
- `ntdll!RtlLeaveCriticalSection` at `0x180010bf1`
- `ntdll!RtlLeaveCriticalSection` at `0x180010d27`
- `ntdll!RtlLeaveCriticalSection` at `0x180010d92`
- `ntdll!RtlLeaveCriticalSection` at `0x180010db2`
- `ntdll!RtlEnterCriticalSection` at `0x180010b3a`
- `ntdll!RtlEnterCriticalSection` at `0x180010ce6`
- `ntdll!RtlEnterCriticalSection` at `0x180010b3a`
- `ntdll!RtlEnterCriticalSection` at `0x180010ce6`
- `ntdll!RtlInitUnicodeString` at `0x1800107a5`
- `ntdll!RtlInitUnicodeString` at `0x1800107a5`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180010d44`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180010d44`

## pseudocode

```c
__int64 __fastcall LRPC_CASSOCIATION::AlpcConnect(
        LRPC_CASSOCIATION *this,
        int a2,
        unsigned int a3,
        int a4,
        void *a5,
        int *a6)
{
  __int64 v6; // rdi
  const unsigned __int16 *v9; // rbx
  unsigned __int16 *v10; // rax
  WCHAR *v11; // r12
  int v12; // r13d
  int v13; // ebx
  int v14; // ecx
  char v15; // dl
  char v16; // r8
  int v17; // r9d
  int v18; // ecx
  int v19; // ecx
  __int64 *v20; // rax
  int v21; // ecx
  SID *v22; // r15
  int v23; // esi
  PSECURITY_DESCRIPTOR v24; // rdx
  unsigned int v25; // eax
  unsigned __int64 v26; // rdi
  unsigned int v27; // ebx
  unsigned __int16 v29; // r8
  _DWORD *v30; // rax
  LRPC_CLIENT_IO *v31; // rcx
  struct _RTL_CRITICAL_SECTION *v32; // rcx
  int v33; // [rsp+28h] [rbp-D8h]
  unsigned int i; // [rsp+60h] [rbp-A0h]
  __int64 v36; // [rsp+68h] [rbp-98h] BYREF
  void *v37; // [rsp+70h] [rbp-90h]
  int v38; // [rsp+78h] [rbp-88h]
  unsigned int v39; // [rsp+7Ch] [rbp-84h]
  __int64 *v40; // [rsp+80h] [rbp-80h]
  int *v41; // [rsp+88h] [rbp-78h]
  struct _UNICODE_STRING UnicodeString; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v44; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v45; // [rsp+C0h] [rbp-40h]
  __int128 v46; // [rsp+D0h] [rbp-30h]
  __int128 v47; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v48; // [rsp+F0h] [rbp-10h]
  __int128 v49; // [rsp+100h] [rbp+0h]
  _DWORD v50[3]; // [rsp+110h] [rbp+10h] BYREF
  char v51; // [rsp+11Ch] [rbp+1Ch]
  char v52; // [rsp+11Dh] [rbp+1Dh]
  __int64 v53; // [rsp+120h] [rbp+20h]
  __int64 v54; // [rsp+128h] [rbp+28h]
  __int64 v55; // [rsp+130h] [rbp+30h]
  __int64 v56; // [rsp+138h] [rbp+38h]
  __int64 v57; // [rsp+140h] [rbp+40h]
  __int64 v58; // [rsp+148h] [rbp+48h]
  int v59; // [rsp+150h] [rbp+50h]
  __int64 v60; // [rsp+160h] [rbp+60h] BYREF

  v6 = a3;
  v38 = a4;
  v39 = a3;
  v37 = a5;
  v41 = a6;
  DestinationString = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  memset_0(v50, 0, 0x48u);
  *a6 = 0;
  v9 = (const unsigned __int16 *)*((_QWORD *)this + 10);
  v36 = 0;
  UnicodeString = 0;
  if ( wcsstr(v9, L"\\RPC Control\\") )
  {
    v10 = DuplicateString(v9);
  }
  else
  {
    if ( (int)RtlGetAppContainerNamedObjectPath(0, 0, 0, &UnicodeString) >= 0 && UnicodeString.Buffer )
    {
      v11 = DuplicateString3(UnicodeString.Buffer, L"\\RPC Control\\", v9);
      RtlFreeUnicodeString(&UnicodeString);
      goto LABEL_6;
    }
    v10 = DuplicateString3(&Src, L"\\RPC Control\\", v9);
  }
  v11 = v10;
LABEL_6:
  if ( !v11 )
  {
    v27 = 14;
    goto LABEL_30;
  }
  v12 = 0;
  v13 = 0;
  RtlInitUnicodeString(&DestinationString, v11);
  v14 = *((_DWORD *)this + 18);
  v15 = *((_BYTE *)this + 220);
  v16 = *((_BYTE *)this + 212);
  v17 = *((_DWORD *)this + 54) - 1;
  *(_QWORD *)&v48 = &DestinationString;
  v55 = 0xFFFFFFFFLL;
  v56 = 0xFFFFFFFFLL;
  v58 = 0xFFFFFFFFLL;
  v57 = 0xFFFFFFFFLL;
  LODWORD(v44) = 48;
  *((_QWORD *)&v44 + 1) = 0;
  DWORD2(v45) = 0;
  *(_QWORD *)&v45 = 0;
  LODWORD(v47) = 48;
  *((_QWORD *)&v47 + 1) = 0;
  DWORD2(v48) = 0;
  v59 = 4093;
  v53 = 4096;
  v54 = 0;
  v50[0] = 34144256;
  v46 = 0;
  v49 = 0;
  v18 = v14 - 1;
  if ( v18 )
  {
    v19 = v18 - 1;
    if ( v19 )
    {
      if ( v19 == 1 )
        v50[0] = 42532864;
    }
    else
    {
      v50[0] = 38338560;
    }
  }
  else
  {
    v50[0] = 36241408;
  }
  v50[1] = 12;
  v51 = v16;
  v52 = v15;
  v50[2] = v17;
  if ( a2 )
  {
    v21 = 0;
    v20 = 0;
  }
  else
  {
    if ( (_DWORD)v6 )
    {
      if ( (_DWORD)v6 == -1 )
        v36 = 0x8000000000000000uLL;
      else
        v36 = -10000 * v6;
      v20 = &v36;
    }
    else
    {
      v20 = 0;
    }
    v21 = 0x20000;
  }
  v22 = (SID *)*((_QWORD *)this + 24);
  v23 = 0;
  v40 = v20;
  for ( i = v21; ; v21 = i )
  {
    v24 = v37;
    v60 = 0;
    if ( !v22 )
    {
      if ( !v37 )
        v24 = gDefaultSecurityDescriptor;
      v37 = v24;
    }
    if ( v24 )
    {
      v33 = (int)v24;
      v26 = (unsigned int)NtAlpcConnectPortEx((char *)this + 136, &v47, &v44, v50, v21);
      LogEvent(0x4Cu, 0x63u, (void *)v26, v37, i, v33, 0);
    }
    else
    {
      v25 = NtAlpcConnectPort((char *)this + 136, &DestinationString, &v44, v50, v21, v22, 0, 0, 0, &v60, v20);
      LODWORD(v26) = v25;
      if ( dword_1800FE624 )
        LogEventToEtw(0x4Cu, 0x63u, v25, (__int64)v22, i);
    }
    if ( (int)v26 <= -1073741759 )
    {
      if ( (_DWORD)v26 == -1073741759 || (_DWORD)v26 == -1073741801 )
      {
LABEL_102:
        v27 = 14;
        goto LABEL_28;
      }
      if ( (_DWORD)v26 == -1073741790 )
      {
LABEL_61:
        v27 = 5;
        goto LABEL_28;
      }
      if ( (_DWORD)v26 != -1073741772 )
      {
        if ( (_DWORD)v26 == -1073741770 )
        {
          v27 = 1834;
          goto LABEL_28;
        }
        if ( (_DWORD)v26 == -1073741767 )
        {
          v27 = 1706;
          goto LABEL_28;
        }
      }
      goto LABEL_27;
    }
    switch ( (_DWORD)v26 )
    {
      case 0xC00000A5:
        goto LABEL_61;
      case 0xC0000044:
        goto LABEL_102;
      case 0xC000009A:
        v27 = 1721;
        goto LABEL_28;
    }
    if ( (_DWORD)v26 != -1073741152 )
      break;
    if ( !v38 || v23 )
    {
      v29 = 11;
      goto LABEL_74;
    }
    if ( !v13 )
    {
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 144));
      if ( (*((_DWORD *)this + 52) & 1) != 0 )
      {
        v27 = 1818;
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 144));
        goto LABEL_64;
      }
      v30 = AllocWrapper(0x60u);
      if ( v30 )
      {
        v30[2] = -1985229329;
        v30[4] = 1;
        *(_QWORD *)v30 = &REFERENCED_CLIENT_IO::`vftable';
        v30[12] = 0;
        *((_QWORD *)v30 + 8) = 0;
        *((_QWORD *)v30 + 9) = 0;
        *((_QWORD *)v30 + 11) = 0;
        v30[3] = 2;
      }
      else
      {
        v30 = 0;
      }
      *((_QWORD *)this + 33) = v30;
      if ( !v30 )
      {
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 144));
        v27 = 14;
        goto LABEL_29;
      }
      v31 = (LRPC_CLIENT_IO *)(v30 + 6);
      if ( a2 )
        LRPC_CLIENT_IO::FullReinitAsync(v31, (void (*)(void *))LrpcRetryAlpcConnect, this);
      else
        LRPC_CLIENT_IO::FullReinitSync(v31);
      _InterlockedOr((volatile signed __int32 *)(*((_QWORD *)this + 33) + 48LL), 2u);
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 144));
      if ( g_pMachineAccountSid )
      {
        v27 = 0;
      }
      else
      {
        v27 = LrpcPrepareMachineAccountSid(a2, (struct LRPC_CLIENT_IO *)(*((_QWORD *)this + 33) + 24LL), v39);
        if ( v27 == -1073606632 )
          goto LABEL_29;
      }
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 144));
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 33) + 32LL))(*((_QWORD *)this + 33));
      *((_QWORD *)this + 33) = 0;
      v32 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 144);
      if ( v27 )
      {
        RtlLeaveCriticalSection(v32);
        goto LABEL_28;
      }
      if ( (*((_DWORD *)this + 52) & 1) != 0 )
      {
        v27 = 1818;
        RtlLeaveCriticalSection(v32);
LABEL_64:
        RpcpErrorAddRecord(2u, 1818, 0xCu, 0, 0);
LABEL_28:
        RpcpErrorAddRecord(2u, v27, 0xAu, v11, v26);
        goto LABEL_29;
      }
      RtlLeaveCriticalSection(v32);
      if ( !g_pMachineAccountSid || !EqualSid(g_pMachineAccountSid, *((PSID *)this + 24)) )
      {
        v29 = 13;
LABEL_74:
        v27 = -1073606633;
        RpcpErrorAddRecord(2u, -1073606633, v29, 0, 0);
        goto LABEL_28;
      }
      v13 = 1;
LABEL_89:
      v22 = &LocalSystem;
      v12 = 1;
LABEL_90:
      v23 = 0;
      goto LABEL_56;
    }
    if ( !v12 )
      goto LABEL_89;
    if ( v12 == 1 )
    {
      v22 = &LocalService;
      v12 = 2;
      goto LABEL_90;
    }
    v23 = 1;
    v22 = &NetworkService;
    v12 = 0;
LABEL_56:
    v20 = v40;
  }
  if ( (_DWORD)v26 == -1073740031 )
    goto LABEL_97;
  if ( (_DWORD)v26 )
  {
    if ( (_DWORD)v26 != 258 )
    {
LABEL_27:
      v27 = 1722;
      goto LABEL_28;
    }
LABEL_97:
    v27 = 1818;
    goto LABEL_28;
  }
  if ( !(unsigned int)IsPortWithSharedSection(*((void **)this + 17)) )
    *((_DWORD *)this + 144) = 65280;
  if ( a2 )
  {
    v27 = -1073606632;
    *v41 = 1;
  }
  else
  {
    v27 = 0;
  }
LABEL_29:
  FreeWrapper(v11);
LABEL_30:
  if ( (*((_DWORD *)this + 52) & 0x400) != 0 && (v27 == 5 || v27 == -1073606633) )
    return 1722;
  return v27;
}

```

## disassembly

```asm
0x180010690  mov     [rsp-8+arg_18], rbx
0x180010695  push    rbp
0x180010696  push    rsi
0x180010697  push    rdi
0x180010698  push    r12
0x18001069a  push    r13
0x18001069c  push    r14
0x18001069e  push    r15
0x1800106a0  lea     rbp, [rsp-70h]
0x1800106a5  sub     rsp, 170h
0x1800106ac  mov     rax, cs:__security_cookie
0x1800106b3  xor     rax, rsp
0x1800106b6  mov     [rbp+0A0h+var_38], rax
0x1800106ba  mov     rbx, [rbp+0A0h+arg_28]
0x1800106c1  xorps   xmm0, xmm0
0x1800106c4  xorps   xmm1, xmm1
0x1800106c7  mov     edi, r8d
0x1800106ca  mov     esi, edx
0x1800106cc  mov     dword ptr [rsp+1A0h+var_140+4], edx
0x1800106d0  xor     edx, edx; Val
0x1800106d2  mov     [rsp+1A0h+var_128], r9d
0x1800106d7  mov     r9, [rbp+0A0h+arg_20]
0x1800106de  mov     r14, rcx
0x1800106e1  lea     rcx, [rbp+0A0h+var_90]; void *
0x1800106e5  mov     [rsp+1A0h+var_124], edi
0x1800106e9  mov     [rsp+1A0h+var_130], r9
0x1800106ee  lea     r8d, [rdx+48h]; Size
0x1800106f2  mov     [rbp+0A0h+var_118], rbx
0x1800106f6  movups  xmmword ptr [rbp+0A0h+DestinationString.Length], xmm0
0x1800106fa  movups  [rbp+0A0h+var_C0], xmm1
0x1800106fe  movups  [rbp+0A0h+var_B0], xmm1
0x180010702  movups  [rbp+0A0h+var_A0], xmm1
0x180010706  movups  [rbp+0A0h+var_F0], xmm0
0x18001070a  movups  [rbp+0A0h+var_E0], xmm0
0x18001070e  movups  [rbp+0A0h+var_D0], xmm0
0x180010712  call    memset_0
0x180010717  mov     dword ptr [rbx], 0
0x18001071d  lea     r15, aRpcControl; "\\RPC Control\\"
0x180010724  mov     rbx, [r14+50h]
0x180010728  xorps   xmm0, xmm0
0x18001072b  mov     rcx, rbx; Str
0x18001072e  mov     [rsp+1A0h+var_138], 0
0x180010737  mov     rdx, r15; SubStr
0x18001073a  movups  xmmword ptr [rbp+0A0h+UnicodeString.Length], xmm0
0x18001073e  call    cs:__imp_wcsstr
0x180010745  nop     dword ptr [rax+rax+00h]
0x18001074a  test    rax, rax
0x18001074d  jnz     loc_180010A75
0x180010753  lea     r9, [rbp+0A0h+UnicodeString]
0x180010757  xor     r8d, r8d
0x18001075a  xor     edx, edx
0x18001075c  xor     ecx, ecx
0x18001075e  call    cs:__imp_RtlGetAppContainerNamedObjectPath
0x180010765  nop     dword ptr [rax+rax+00h]
0x18001076a  test    eax, eax
0x18001076c  js      short loc_18001077B
0x18001076e  mov     rcx, [rbp+0A0h+UnicodeString.Buffer]; Src
0x180010772  test    rcx, rcx
0x180010775  jnz     loc_180010B03
0x18001077b  mov     r8, rbx; unsigned __int16 *
0x18001077e  lea     rcx, Src; Src
0x180010785  mov     rdx, r15; unsigned __int16 *
0x180010788  call    ?DuplicateString3@@YAPEAGPEBG00@Z; DuplicateString3(ushort const *,ushort const *,ushort const *)
0x18001078d  mov     r12, rax
0x180010790  test    r12, r12
0x180010793  jz      loc_1800109C7
0x180010799  mov     rdx, r12; SourceString
0x18001079c  lea     rcx, [rbp+0A0h+DestinationString]; DestinationString
0x1800107a0  xor     r13d, r13d
0x1800107a3  xor     ebx, ebx
0x1800107a5  call    cs:__imp_RtlInitUnicodeString
0x1800107ac  nop     dword ptr [rax+rax+00h]
0x1800107b1  mov     r9d, [r14+0D8h]
0x1800107b8  lea     rax, [rbp+0A0h+DestinationString]
0x1800107bc  mov     ecx, [r14+48h]
0x1800107c0  xor     r11d, r11d
0x1800107c3  mov     dl, [r14+0DCh]
0x1800107ca  xorps   xmm0, xmm0
0x1800107cd  mov     r8b, [r14+0D4h]
0x1800107d4  dec     r9d
0x1800107d7  mov     qword ptr [rbp+0A0h+var_B0], rax
0x1800107db  mov     eax, 0FFFFFFFFh
0x1800107e0  mov     [rbp+0A0h+var_70], rax
0x1800107e4  mov     [rbp+0A0h+var_68], rax
0x1800107e8  mov     [rbp+0A0h+var_58], rax
0x1800107ec  mov     [rbp+0A0h+var_60], rax
0x1800107f0  mov     dword ptr [rbp+0A0h+var_F0], 30h ; '0'
0x1800107f7  mov     qword ptr [rbp+0A0h+var_F0+8], r11
0x1800107fb  mov     dword ptr [rbp+0A0h+var_E0+8], r11d
0x1800107ff  mov     qword ptr [rbp+0A0h+var_E0], r11
0x180010803  mov     dword ptr [rbp+0A0h+var_C0], 30h ; '0'
0x18001080a  mov     qword ptr [rbp+0A0h+var_C0+8], r11
0x18001080e  mov     dword ptr [rbp+0A0h+var_B0+8], r11d
0x180010812  mov     [rbp+0A0h+var_50], 0FFDh
0x180010819  mov     [rbp+0A0h+var_80], 1000h
0x180010821  mov     [rbp+0A0h+var_78], r11
0x180010825  mov     [rbp+0A0h+var_90], 2090000h
0x18001082c  movdqu  [rbp+0A0h+var_D0], xmm0
0x180010831  movdqu  [rbp+0A0h+var_A0], xmm0
0x180010836  sub     ecx, 1
0x180010839  jz      loc_180010C33
0x18001083f  sub     ecx, 1
0x180010842  jz      loc_180010B8B
0x180010848  cmp     ecx, 1
0x18001084b  jz      loc_180010C27
0x180010851  mov     [rbp+0A0h+var_8C], 0Ch
0x180010858  mov     [rbp+0A0h+var_84], r8b
0x18001085c  mov     [rbp+0A0h+var_83], dl
0x18001085f  mov     [rbp+0A0h+var_88], r9d
0x180010863  test    esi, esi
0x180010865  jnz     loc_180010A97
0x18001086b  test    edi, edi
0x18001086d  jnz     loc_180010B97
0x180010873  mov     rax, r11
0x180010876  mov     ecx, 20000h
0x18001087b  mov     r15, [r14+0C0h]
0x180010882  mov     esi, r11d
0x180010885  mov     [rbp+0A0h+var_120], rax
0x180010889  mov     dword ptr [rsp+1A0h+var_140], ecx
0x18001088d  lea     r10, [r14+88h]
0x180010894  mov     rdx, [rsp+1A0h+var_130]
0x180010899  mov     [rbp+0A0h+var_40], 0
0x1800108a1  test    r15, r15
0x1800108a4  jz      loc_180010A82
0x1800108aa  mov     [rsp+1A0h+var_150], rax
0x1800108af  lea     rax, [rbp+0A0h+var_40]
0x1800108b3  mov     [rsp+1A0h+var_158], rax
0x1800108b8  lea     r9, [rbp+0A0h+var_90]
0x1800108bc  mov     [rsp+1A0h+var_160], r11
0x1800108c1  lea     r8, [rbp+0A0h+var_F0]
0x1800108c5  mov     [rsp+1A0h+var_168], r11
0x1800108ca  mov     qword ptr [rsp+1A0h+var_170], r11; int
0x1800108cf  test    rdx, rdx
0x1800108d2  jnz     loc_180010A38
0x1800108d8  mov     qword ptr [rsp+1A0h+var_178], r15
0x1800108dd  lea     rdx, [rbp+0A0h+DestinationString]
0x1800108e1  mov     dword ptr [rsp+1A0h+var_180], ecx
0x1800108e5  mov     rcx, r10
0x1800108e8  call    cs:__imp_NtAlpcConnectPort
0x1800108ef  nop     dword ptr [rax+rax+00h]
0x1800108f4  xor     r11d, r11d
0x1800108f7  mov     edi, eax
0x1800108f9  cmp     cs:dword_1800FE624, r11d
0x180010900  jz      short loc_18001091D
0x180010902  mov     ecx, dword ptr [rsp+1A0h+var_140]
0x180010906  mov     r8d, edi; __int64
0x180010909  mov     [rsp+1A0h+var_180], rcx; __int64
0x18001090e  mov     r9, r15; __int64
0x180010911  mov     cl, 4Ch ; 'L'; unsigned __int8
0x180010913  mov     dl, 63h ; 'c'; unsigned __int8
0x180010915  call    ?LogEventToEtw@@YAXEE_J00@Z; LogEventToEtw(uchar,uchar,__int64,__int64,__int64)
0x18001091a  xor     r11d, r11d
0x18001091d  cmp     edi, 0C0000041h
0x180010923  jg      loc_1800109CE
0x180010929  jz      loc_180010E37
0x18001092f  cmp     edi, 0C0000017h
0x180010935  jz      loc_180010E37
0x18001093b  cmp     edi, 0C0000022h
0x180010941  jz      loc_180010B26
0x180010947  cmp     edi, 0C0000034h
0x18001094d  jz      short loc_180010967
0x18001094f  cmp     edi, 0C0000036h
0x180010955  jz      loc_180010E2D
0x18001095b  cmp     edi, 0C0000039h
0x180010961  jz      loc_180010E17
0x180010967  mov     ebx, 6BAh
0x18001096c  mov     r8d, 0Ah; unsigned __int16
0x180010972  mov     dword ptr [rsp+1A0h+var_180], edi; unsigned int
0x180010976  mov     r9, r12; unsigned __int16 *
0x180010979  mov     edx, ebx; int
0x18001097b  lea     ecx, [r8-8]; unsigned int
0x18001097f  call    ?RpcpErrorAddRecord@@YAXKJGPEAGK@Z; RpcpErrorAddRecord(ulong,long,ushort,ushort *,ulong)
0x180010984  mov     rcx, r12; lpMem
0x180010987  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18001098c  mov     eax, [r14+0D0h]
0x180010993  bt      eax, 0Ah
0x180010997  jb      loc_180010AE8
0x18001099d  mov     eax, ebx
0x18001099f  mov     rcx, [rbp+0A0h+var_38]
0x1800109a3  xor     rcx, rsp; StackCookie
0x1800109a6  call    __security_check_cookie
0x1800109ab  mov     rbx, [rsp+1A0h+arg_18]
0x1800109b3  add     rsp, 170h
0x1800109ba  pop     r15
0x1800109bc  pop     r14
0x1800109be  pop     r13
0x1800109c0  pop     r12
0x1800109c2  pop     rdi
0x1800109c3  pop     rsi
0x1800109c4  pop     rbp
0x1800109c5  retn
0x1800109c7  mov     ebx, 0Eh
0x1800109cc  jmp     short loc_18001098C
0x1800109ce  cmp     edi, 0C00000A5h
0x1800109d4  jz      loc_180010B26
0x1800109da  cmp     edi, 0C0000044h
0x1800109e0  jz      loc_180010E37
0x1800109e6  cmp     edi, 0C000009Ah
0x1800109ec  jz      loc_180010E0D
0x1800109f2  cmp     edi, 0C00002A0h
0x1800109f8  jz      loc_180010AA2
0x1800109fe  cmp     edi, 0C0000701h
0x180010a04  jz      loc_180010DDF
0x180010a0a  test    edi, edi
0x180010a0c  jnz     loc_180010DD3
0x180010a12  mov     rcx, [r14+88h]; void *
0x180010a19  call    ?IsPortWithSharedSection@@YAHPEAX@Z; IsPortWithSharedSection(void *)
0x180010a1e  test    eax, eax
0x180010a20  jz      loc_180010DE9
0x180010a26  cmp     dword ptr [rsp+1A0h+var_140+4], 0
0x180010a2b  jnz     loc_180010DF9
0x180010a31  xor     ebx, ebx
0x180010a33  jmp     loc_180010984
0x180010a38  mov     qword ptr [rsp+1A0h+var_178], rdx; int
0x180010a3d  lea     rdx, [rbp+0A0h+var_C0]
0x180010a41  mov     dword ptr [rsp+1A0h+var_180], ecx
0x180010a45  mov     rcx, r10
0x180010a48  call    cs:__imp_NtAlpcConnectPortEx
0x180010a4f  nop     dword ptr [rax+rax+00h]
0x180010a54  mov     r9, [rsp+1A0h+var_130]; void *
0x180010a59  mov     dl, 63h ; 'c'; unsigned __int8
0x180010a5b  mov     edi, eax
0x180010a5d  mov     cl, 4Ch ; 'L'; unsigned __int8
0x180010a5f  mov     eax, dword ptr [rsp+1A0h+var_140]
0x180010a63  mov     r8d, edi; void *
0x180010a66  mov     [rsp+1A0h+var_180], rax; unsigned __int64
0x180010a6b  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x180010a70  jmp     loc_18001091A
0x180010a75  mov     rcx, rbx; Src
0x180010a78  call    ?DuplicateString@@YAPEAGPEBG@Z; DuplicateString(ushort const *)
0x180010a7d  jmp     loc_18001078D
0x180010a82  test    rdx, rdx
0x180010a85  cmovz   rdx, cs:?gDefaultSecurityDescriptor@@3PEAXEA; void * gDefaultSecurityDescriptor
0x180010a8d  mov     [rsp+1A0h+var_130], rdx
0x180010a92  jmp     loc_1800108AA
0x180010a97  mov     ecx, r11d
0x180010a9a  mov     rax, r11
0x180010a9d  jmp     loc_18001087B
0x180010aa2  cmp     [rsp+1A0h+var_128], r11d
0x180010aa7  jz      loc_180010DC8
0x180010aad  test    esi, esi
0x180010aaf  jnz     loc_180010DC8
0x180010ab5  test    ebx, ebx
0x180010ab7  jz      short loc_180010B30
0x180010ab9  mov     ecx, r13d
0x180010abc  test    r13d, r13d
0x180010abf  jz      loc_180010D5F
0x180010ac5  sub     ecx, 1
0x180010ac8  jz      loc_180010D83
0x180010ace  mov     esi, 1
0x180010ad3  cmp     ecx, esi
0x180010ad5  jz      loc_180010D74
0x180010adb  mov     rax, [rbp+0A0h+var_120]
0x180010adf  mov     ecx, dword ptr [rsp+1A0h+var_140]
0x180010ae3  jmp     loc_18001088D
0x180010ae8  cmp     ebx, 5
0x180010aeb  jz      short loc_180010AF9
0x180010aed  cmp     ebx, 0C0021017h
0x180010af3  jnz     loc_18001099D
0x180010af9  mov     ebx, 6BAh
0x180010afe  jmp     loc_18001099D
0x180010b03  mov     r8, rbx; unsigned __int16 *
0x180010b06  mov     rdx, r15; unsigned __int16 *
0x180010b09  call    ?DuplicateString3@@YAPEAGPEBG00@Z; DuplicateString3(ushort const *,ushort const *,ushort const *)
0x180010b0e  lea     rcx, [rbp+0A0h+UnicodeString]; UnicodeString
0x180010b12  mov     r12, rax
0x180010b15  call    cs:__imp_RtlFreeUnicodeString
0x180010b1c  nop     dword ptr [rax+rax+00h]
0x180010b21  jmp     loc_180010790
0x180010b26  mov     ebx, 5
0x180010b2b  jmp     loc_18001096C
0x180010b30  lea     rsi, [r14+90h]
0x180010b37  mov     rcx, rsi; CriticalSection
0x180010b3a  call    cs:__imp_RtlEnterCriticalSection
0x180010b41  nop     dword ptr [rax+rax+00h]
0x180010b46  mov     eax, [r14+0D0h]
0x180010b4d  test    al, 1
0x180010b4f  jz      loc_180010C3F
0x180010b55  mov     rcx, rsi; CriticalSection
0x180010b58  mov     ebx, 71Ah
0x180010b5d  call    cs:__imp_RtlLeaveCriticalSection
0x180010b64  nop     dword ptr [rax+rax+00h]
0x180010b69  mov     [rsp+1A0h+var_180], 0; struct tagParam *
0x180010b72  mov     r8d, 0Ch; unsigned __int16
0x180010b78  mov     edx, ebx; int
0x180010b7a  xor     r9d, r9d; int
0x180010b7d  lea     ecx, [r9+2]; unsigned int
0x180010b81  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180010b86  jmp     loc_18001096C
0x180010b8b  mov     [rbp+0A0h+var_90], 2490000h
0x180010b92  jmp     loc_180010851
0x180010b97  cmp     edi, 0FFFFFFFFh
0x180010b9a  jnz     short loc_180010BB3
0x180010b9c  mov     dword ptr [rsp+1A0h+var_138], r11d
0x180010ba1  mov     dword ptr [rsp+1A0h+var_138+4], 80000000h
0x180010ba9  lea     rax, [rsp+1A0h+var_138]
0x180010bae  jmp     loc_180010876
0x180010bb3  imul    rcx, rdi, 0FFFFFFFFFFFFD8F0h
0x180010bba  mov     [rsp+1A0h+var_138], rcx
0x180010bbf  jmp     short loc_180010BA9
  ... truncated ...
```
