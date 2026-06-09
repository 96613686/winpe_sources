# LRPC_CASSOCIATION::AlpcConnect(int,ulong,int,void *,int *)

- ea: `0x18004fcf8`
- end: `0x18005044e`
- name: `?AlpcConnect@LRPC_CASSOCIATION@@AEAAJHKHPEAXPEAH@Z`
- size: `1878`
- prototype: `__int64 __usercall@<rax>(LRPC_CASSOCIATION *__hidden this@<rcx>, int@<edx>, unsigned int@<r8d>, int@<r9d>, void *, int *)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180029798`
- `0x1800b8e54`

## callees

- `0x180021ce0`
- `0x180021e70`
- `0x180022870`
- `0x1800274e0`
- `0x1800283bc`
- `0x18002d420`
- `0x18004fcf8`
- `0x180050500`
- `0x1800505f0`
- `0x180050708`
- `0x1800637f0`
- `0x18009ee0c`
- `0x1800a4c50`
- `0x1800ca049`
- `0x1800ca140`
- `0x1800d2010`

## import_xrefs

- `ntdll!NtAlpcConnectPortEx` at `0x180050097`
- `ntdll!NtAlpcConnectPortEx` at `0x180050097`
- `ntdll!NtAlpcConnectPort` at `0x18004ff3e`
- `ntdll!NtAlpcConnectPort` at `0x18004ff3e`
- `ntdll!wcsstr` at `0x18004fda6`
- `ntdll!wcsstr` at `0x18004fda6`
- `ntdll!RtlGetAppContainerNamedObjectPath` at `0x18004fdc0`
- `ntdll!RtlGetAppContainerNamedObjectPath` at `0x18004fdc0`
- `ntdll!RtlFreeUnicodeString` at `0x18005015e`
- `ntdll!RtlFreeUnicodeString` at `0x18005015e`
- `ntdll!RtlLeaveCriticalSection` at `0x18005019a`
- `ntdll!RtlLeaveCriticalSection` at `0x180050207`
- `ntdll!RtlLeaveCriticalSection` at `0x180050222`
- `ntdll!RtlLeaveCriticalSection` at `0x18005034c`
- `ntdll!RtlLeaveCriticalSection` at `0x1800503ab`
- `ntdll!RtlLeaveCriticalSection` at `0x1800503c5`
- `ntdll!RtlLeaveCriticalSection` at `0x18005019a`
- `ntdll!RtlLeaveCriticalSection` at `0x180050207`
- `ntdll!RtlLeaveCriticalSection` at `0x180050222`
- `ntdll!RtlLeaveCriticalSection` at `0x18005034c`
- `ntdll!RtlLeaveCriticalSection` at `0x1800503ab`
- `ntdll!RtlLeaveCriticalSection` at `0x1800503c5`
- `ntdll!RtlEnterCriticalSection` at `0x18005017d`
- `ntdll!RtlEnterCriticalSection` at `0x180050311`
- `ntdll!RtlEnterCriticalSection` at `0x18005017d`
- `ntdll!RtlEnterCriticalSection` at `0x180050311`
- `ntdll!RtlInitUnicodeString` at `0x18004fe01`
- `ntdll!RtlInitUnicodeString` at `0x18004fe01`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180050363`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180050363`

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
      if ( dword_1800F9624 )
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
0x18004fcf8  mov     [rsp-8+arg_18], rbx
0x18004fcfd  push    rbp
0x18004fcfe  push    rsi
0x18004fcff  push    rdi
0x18004fd00  push    r12
0x18004fd02  push    r13
0x18004fd04  push    r14
0x18004fd06  push    r15
0x18004fd08  lea     rbp, [rsp-70h]
0x18004fd0d  sub     rsp, 170h
0x18004fd14  mov     rax, cs:__security_cookie
0x18004fd1b  xor     rax, rsp
0x18004fd1e  mov     [rbp+0A0h+var_38], rax
0x18004fd22  mov     rbx, [rbp+0A0h+arg_28]
0x18004fd29  xorps   xmm0, xmm0
0x18004fd2c  xorps   xmm1, xmm1
0x18004fd2f  mov     edi, r8d
0x18004fd32  mov     esi, edx
0x18004fd34  mov     dword ptr [rsp+1A0h+var_140+4], edx
0x18004fd38  xor     edx, edx; Val
0x18004fd3a  mov     [rsp+1A0h+var_128], r9d
0x18004fd3f  mov     r9, [rbp+0A0h+arg_20]
0x18004fd46  mov     r14, rcx
0x18004fd49  lea     rcx, [rbp+0A0h+var_90]; void *
0x18004fd4d  mov     [rsp+1A0h+var_124], edi
0x18004fd51  mov     [rsp+1A0h+var_130], r9
0x18004fd56  lea     r8d, [rdx+48h]; Size
0x18004fd5a  mov     [rbp+0A0h+var_118], rbx
0x18004fd5e  movups  xmmword ptr [rbp+0A0h+DestinationString.Length], xmm0
0x18004fd62  movups  [rbp+0A0h+var_C0], xmm1
0x18004fd66  movups  [rbp+0A0h+var_B0], xmm1
0x18004fd6a  movups  [rbp+0A0h+var_A0], xmm1
0x18004fd6e  movups  [rbp+0A0h+var_F0], xmm0
0x18004fd72  movups  [rbp+0A0h+var_E0], xmm0
0x18004fd76  movups  [rbp+0A0h+var_D0], xmm0
0x18004fd7a  call    memset_0
0x18004fd7f  mov     dword ptr [rbx], 0
0x18004fd85  lea     r15, aRpcControl; "\\RPC Control\\"
0x18004fd8c  mov     rbx, [r14+50h]
0x18004fd90  xorps   xmm0, xmm0
0x18004fd93  mov     rcx, rbx; Str
0x18004fd96  mov     [rsp+1A0h+var_138], 0
0x18004fd9f  mov     rdx, r15; SubStr
0x18004fda2  movups  xmmword ptr [rbp+0A0h+UnicodeString.Length], xmm0
0x18004fda6  call    cs:__imp_wcsstr
0x18004fdac  test    rax, rax
0x18004fdaf  jnz     loc_1800500BE
0x18004fdb5  lea     r9, [rbp+0A0h+UnicodeString]
0x18004fdb9  xor     r8d, r8d
0x18004fdbc  xor     edx, edx
0x18004fdbe  xor     ecx, ecx
0x18004fdc0  call    cs:__imp_RtlGetAppContainerNamedObjectPath
0x18004fdc6  test    eax, eax
0x18004fdc8  js      short loc_18004FDD7
0x18004fdca  mov     rcx, [rbp+0A0h+UnicodeString.Buffer]; Src
0x18004fdce  test    rcx, rcx
0x18004fdd1  jnz     loc_18005014C
0x18004fdd7  mov     r8, rbx; unsigned __int16 *
0x18004fdda  lea     rcx, Src; Src
0x18004fde1  mov     rdx, r15; unsigned __int16 *
0x18004fde4  call    ?DuplicateString3@@YAPEAGPEBG00@Z; DuplicateString3(ushort const *,ushort const *,ushort const *)
0x18004fde9  mov     r12, rax
0x18004fdec  test    r12, r12
0x18004fdef  jz      loc_180050016
0x18004fdf5  mov     rdx, r12; SourceString
0x18004fdf8  lea     rcx, [rbp+0A0h+DestinationString]; DestinationString
0x18004fdfc  xor     r13d, r13d
0x18004fdff  xor     ebx, ebx
0x18004fe01  call    cs:__imp_RtlInitUnicodeString
0x18004fe07  mov     r9d, [r14+0D8h]
0x18004fe0e  lea     rax, [rbp+0A0h+DestinationString]
0x18004fe12  mov     ecx, [r14+48h]
0x18004fe16  xor     r11d, r11d
0x18004fe19  mov     dl, [r14+0DCh]
0x18004fe20  xorps   xmm0, xmm0
0x18004fe23  mov     r8b, [r14+0D4h]
0x18004fe2a  dec     r9d
0x18004fe2d  mov     qword ptr [rbp+0A0h+var_B0], rax
0x18004fe31  mov     eax, 0FFFFFFFFh
0x18004fe36  mov     [rbp+0A0h+var_70], rax
0x18004fe3a  mov     [rbp+0A0h+var_68], rax
0x18004fe3e  mov     [rbp+0A0h+var_58], rax
0x18004fe42  mov     [rbp+0A0h+var_60], rax
0x18004fe46  mov     dword ptr [rbp+0A0h+var_F0], 30h ; '0'
0x18004fe4d  mov     qword ptr [rbp+0A0h+var_F0+8], r11
0x18004fe51  mov     dword ptr [rbp+0A0h+var_E0+8], r11d
0x18004fe55  mov     qword ptr [rbp+0A0h+var_E0], r11
0x18004fe59  mov     dword ptr [rbp+0A0h+var_C0], 30h ; '0'
0x18004fe60  mov     qword ptr [rbp+0A0h+var_C0+8], r11
0x18004fe64  mov     dword ptr [rbp+0A0h+var_B0+8], r11d
0x18004fe68  mov     [rbp+0A0h+var_50], 0FFDh
0x18004fe6f  mov     [rbp+0A0h+var_80], 1000h
0x18004fe77  mov     [rbp+0A0h+var_78], r11
0x18004fe7b  mov     [rbp+0A0h+var_90], 2090000h
0x18004fe82  movdqu  [rbp+0A0h+var_D0], xmm0
0x18004fe87  movdqu  [rbp+0A0h+var_A0], xmm0
0x18004fe8c  sub     ecx, 1
0x18004fe8f  jz      loc_18005025E
0x18004fe95  sub     ecx, 1
0x18004fe98  jz      loc_1800501C2
0x18004fe9e  cmp     ecx, 1
0x18004fea1  jz      loc_180050252
0x18004fea7  mov     [rbp+0A0h+var_8C], 0Ch
0x18004feae  mov     [rbp+0A0h+var_84], r8b
0x18004feb2  mov     [rbp+0A0h+var_83], dl
0x18004feb5  mov     [rbp+0A0h+var_88], r9d
0x18004feb9  test    esi, esi
0x18004febb  jnz     loc_1800500E0
0x18004fec1  test    edi, edi
0x18004fec3  jnz     loc_1800501CE
0x18004fec9  mov     rax, r11
0x18004fecc  mov     ecx, 20000h
0x18004fed1  mov     r15, [r14+0C0h]
0x18004fed8  mov     esi, r11d
0x18004fedb  mov     [rbp+0A0h+var_120], rax
0x18004fedf  mov     dword ptr [rsp+1A0h+var_140], ecx
0x18004fee3  lea     r10, [r14+88h]
0x18004feea  mov     rdx, [rsp+1A0h+var_130]
0x18004feef  mov     [rbp+0A0h+var_40], 0
0x18004fef7  test    r15, r15
0x18004fefa  jz      loc_1800500CB
0x18004ff00  mov     [rsp+1A0h+var_150], rax
0x18004ff05  lea     rax, [rbp+0A0h+var_40]
0x18004ff09  mov     [rsp+1A0h+var_158], rax
0x18004ff0e  lea     r9, [rbp+0A0h+var_90]
0x18004ff12  mov     [rsp+1A0h+var_160], r11
0x18004ff17  lea     r8, [rbp+0A0h+var_F0]
0x18004ff1b  mov     [rsp+1A0h+var_168], r11
0x18004ff20  mov     qword ptr [rsp+1A0h+var_170], r11; int
0x18004ff25  test    rdx, rdx
0x18004ff28  jnz     loc_180050087
0x18004ff2e  mov     qword ptr [rsp+1A0h+var_178], r15
0x18004ff33  lea     rdx, [rbp+0A0h+DestinationString]
0x18004ff37  mov     dword ptr [rsp+1A0h+var_180], ecx
0x18004ff3b  mov     rcx, r10
0x18004ff3e  call    cs:__imp_NtAlpcConnectPort
0x18004ff44  xor     r11d, r11d
0x18004ff47  mov     edi, eax
0x18004ff49  cmp     cs:dword_1800F9624, r11d
0x18004ff50  jz      short loc_18004FF6D
0x18004ff52  mov     ecx, dword ptr [rsp+1A0h+var_140]
0x18004ff56  mov     r8d, edi; __int64
0x18004ff59  mov     [rsp+1A0h+var_180], rcx; __int64
0x18004ff5e  mov     r9, r15; __int64
0x18004ff61  mov     cl, 4Ch ; 'L'; unsigned __int8
0x18004ff63  mov     dl, 63h ; 'c'; unsigned __int8
0x18004ff65  call    ?LogEventToEtw@@YAXEE_J00@Z; LogEventToEtw(uchar,uchar,__int64,__int64,__int64)
0x18004ff6a  xor     r11d, r11d
0x18004ff6d  cmp     edi, 0C0000041h
0x18004ff73  jg      loc_18005001D
0x18004ff79  jz      loc_180050444
0x18004ff7f  cmp     edi, 0C0000017h
0x18004ff85  jz      loc_180050444
0x18004ff8b  cmp     edi, 0C0000022h
0x18004ff91  jz      loc_180050169
0x18004ff97  cmp     edi, 0C0000034h
0x18004ff9d  jz      short loc_18004FFB7
0x18004ff9f  cmp     edi, 0C0000036h
0x18004ffa5  jz      loc_18005043A
0x18004ffab  cmp     edi, 0C0000039h
0x18004ffb1  jz      loc_180050424
0x18004ffb7  mov     ebx, 6BAh
0x18004ffbc  mov     r8d, 0Ah; unsigned __int16
0x18004ffc2  mov     dword ptr [rsp+1A0h+var_180], edi; unsigned int
0x18004ffc6  mov     r9, r12; unsigned __int16 *
0x18004ffc9  mov     edx, ebx; int
0x18004ffcb  lea     ecx, [r8-8]; unsigned int
0x18004ffcf  call    ?RpcpErrorAddRecord@@YAXKJGPEAGK@Z; RpcpErrorAddRecord(ulong,long,ushort,ushort *,ulong)
0x18004ffd4  mov     rcx, r12; lpMem
0x18004ffd7  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18004ffdc  mov     eax, [r14+0D0h]
0x18004ffe3  bt      eax, 0Ah
0x18004ffe7  jb      loc_180050131
0x18004ffed  mov     eax, ebx
0x18004ffef  mov     rcx, [rbp+0A0h+var_38]
0x18004fff3  xor     rcx, rsp; StackCookie
0x18004fff6  call    __security_check_cookie
0x18004fffb  mov     rbx, [rsp+1A0h+arg_18]
0x180050003  add     rsp, 170h
0x18005000a  pop     r15
0x18005000c  pop     r14
0x18005000e  pop     r13
0x180050010  pop     r12
0x180050012  pop     rdi
0x180050013  pop     rsi
0x180050014  pop     rbp
0x180050015  retn
0x180050016  mov     ebx, 0Eh
0x18005001b  jmp     short loc_18004FFDC
0x18005001d  cmp     edi, 0C00000A5h
0x180050023  jz      loc_180050169
0x180050029  cmp     edi, 0C0000044h
0x18005002f  jz      loc_180050444
0x180050035  cmp     edi, 0C000009Ah
0x18005003b  jz      loc_18005041A
0x180050041  cmp     edi, 0C00002A0h
0x180050047  jz      loc_1800500EB
0x18005004d  cmp     edi, 0C0000701h
0x180050053  jz      loc_1800503EC
0x180050059  test    edi, edi
0x18005005b  jnz     loc_1800503E0
0x180050061  mov     rcx, [r14+88h]; void *
0x180050068  call    ?IsPortWithSharedSection@@YAHPEAX@Z; IsPortWithSharedSection(void *)
0x18005006d  test    eax, eax
0x18005006f  jz      loc_1800503F6
0x180050075  cmp     dword ptr [rsp+1A0h+var_140+4], 0
0x18005007a  jnz     loc_180050406
0x180050080  xor     ebx, ebx
0x180050082  jmp     loc_18004FFD4
0x180050087  mov     qword ptr [rsp+1A0h+var_178], rdx; int
0x18005008c  lea     rdx, [rbp+0A0h+var_C0]
0x180050090  mov     dword ptr [rsp+1A0h+var_180], ecx
0x180050094  mov     rcx, r10
0x180050097  call    cs:__imp_NtAlpcConnectPortEx
0x18005009d  mov     r9, [rsp+1A0h+var_130]; void *
0x1800500a2  mov     dl, 63h ; 'c'; unsigned __int8
0x1800500a4  mov     edi, eax
0x1800500a6  mov     cl, 4Ch ; 'L'; unsigned __int8
0x1800500a8  mov     eax, dword ptr [rsp+1A0h+var_140]
0x1800500ac  mov     r8d, edi; void *
0x1800500af  mov     [rsp+1A0h+var_180], rax; unsigned __int64
0x1800500b4  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x1800500b9  jmp     loc_18004FF6A
0x1800500be  mov     rcx, rbx; Src
0x1800500c1  call    ?DuplicateString@@YAPEAGPEBG@Z; DuplicateString(ushort const *)
0x1800500c6  jmp     loc_18004FDE9
0x1800500cb  test    rdx, rdx
0x1800500ce  cmovz   rdx, cs:?gDefaultSecurityDescriptor@@3PEAXEA; void * gDefaultSecurityDescriptor
0x1800500d6  mov     [rsp+1A0h+var_130], rdx
0x1800500db  jmp     loc_18004FF00
0x1800500e0  mov     ecx, r11d
0x1800500e3  mov     rax, r11
0x1800500e6  jmp     loc_18004FED1
0x1800500eb  cmp     [rsp+1A0h+var_128], r11d
0x1800500f0  jz      loc_1800503D5
0x1800500f6  test    esi, esi
0x1800500f8  jnz     loc_1800503D5
0x1800500fe  test    ebx, ebx
0x180050100  jz      short loc_180050173
0x180050102  mov     ecx, r13d
0x180050105  test    r13d, r13d
0x180050108  jz      loc_180050378
0x18005010e  sub     ecx, 1
0x180050111  jz      loc_18005039C
0x180050117  mov     esi, 1
0x18005011c  cmp     ecx, esi
0x18005011e  jz      loc_18005038D
0x180050124  mov     rax, [rbp+0A0h+var_120]
0x180050128  mov     ecx, dword ptr [rsp+1A0h+var_140]
0x18005012c  jmp     loc_18004FEE3
0x180050131  cmp     ebx, 5
0x180050134  jz      short loc_180050142
0x180050136  cmp     ebx, 0C0021017h
0x18005013c  jnz     loc_18004FFED
0x180050142  mov     ebx, 6BAh
0x180050147  jmp     loc_18004FFED
0x18005014c  mov     r8, rbx; unsigned __int16 *
0x18005014f  mov     rdx, r15; unsigned __int16 *
0x180050152  call    ?DuplicateString3@@YAPEAGPEBG00@Z; DuplicateString3(ushort const *,ushort const *,ushort const *)
0x180050157  lea     rcx, [rbp+0A0h+UnicodeString]; UnicodeString
0x18005015b  mov     r12, rax
0x18005015e  call    cs:__imp_RtlFreeUnicodeString
0x180050164  jmp     loc_18004FDEC
0x180050169  mov     ebx, 5
0x18005016e  jmp     loc_18004FFBC
0x180050173  lea     rsi, [r14+90h]
0x18005017a  mov     rcx, rsi; CriticalSection
0x18005017d  call    cs:__imp_RtlEnterCriticalSection
0x180050183  mov     eax, [r14+0D0h]
0x18005018a  test    al, 1
0x18005018c  jz      loc_18005026A
0x180050192  mov     rcx, rsi; CriticalSection
0x180050195  mov     ebx, 71Ah
0x18005019a  call    cs:__imp_RtlLeaveCriticalSection
0x1800501a0  mov     [rsp+1A0h+var_180], 0; struct tagParam *
0x1800501a9  mov     r8d, 0Ch; unsigned __int16
0x1800501af  mov     edx, ebx; int
0x1800501b1  xor     r9d, r9d; int
0x1800501b4  lea     ecx, [r9+2]; unsigned int
0x1800501b8  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x1800501bd  jmp     loc_18004FFBC
0x1800501c2  mov     [rbp+0A0h+var_90], 2490000h
0x1800501c9  jmp     loc_18004FEA7
0x1800501ce  cmp     edi, 0FFFFFFFFh
0x1800501d1  jnz     short loc_1800501EA
0x1800501d3  mov     dword ptr [rsp+1A0h+var_138], r11d
0x1800501d8  mov     dword ptr [rsp+1A0h+var_138+4], 80000000h
0x1800501e0  lea     rax, [rsp+1A0h+var_138]
0x1800501e5  jmp     loc_18004FECC
0x1800501ea  imul    rcx, rdi, 0FFFFFFFFFFFFD8F0h
0x1800501f1  mov     [rsp+1A0h+var_138], rcx
0x1800501f6  jmp     short loc_1800501E0
0x1800501f8  mov     rax, [r14+108h]
0x1800501ff  lock or dword ptr [rax+30h], 2
0x180050204  mov     rcx, rsi; CriticalSection
0x180050207  call    cs:__imp_RtlLeaveCriticalSection
0x18005020d  cmp     cs:?g_pMachineAccountSid@@3PEAXEA, r13; void * g_pMachineAccountSid
0x180050214  jz      loc_1800502EA
0x18005021a  mov     ebx, r13d
0x18005021d  jmp     loc_18005030E
  ... truncated ...
```
