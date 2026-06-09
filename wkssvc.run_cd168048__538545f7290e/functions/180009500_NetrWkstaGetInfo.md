# NetrWkstaGetInfo

- ea: `0x180009500`
- end: `0x180009a18`
- name: `NetrWkstaGetInfo`
- size: `1304`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005df0`
- `0x180009500`
- `0x1800204ea`
- `0x1800204f6`
- `0x18002d120`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x180009686`
- `ntdll!RtlAcquireResourceShared` at `0x180009686`
- `ntdll!RtlNtStatusToDosError` at `0x18000998f`
- `ntdll!RtlNtStatusToDosError` at `0x18000998f`
- `ntdll!RtlReleaseResource` at `0x180009981`
- `ntdll!RtlReleaseResource` at `0x1800099a4`
- `ntdll!RtlReleaseResource` at `0x180009981`
- `ntdll!RtlReleaseResource` at `0x1800099a4`
- `ntdll!RtlAdjustPrivilege` at `0x1800095d6`
- `ntdll!RtlAdjustPrivilege` at `0x1800095d6`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x18000964d`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x18000964d`
- `ntdll!RtlInitUnicodeString` at `0x180009582`
- `ntdll!RtlInitUnicodeString` at `0x18000959d`
- `ntdll!RtlInitUnicodeString` at `0x1800095b8`
- `ntdll!RtlInitUnicodeString` at `0x180009582`
- `ntdll!RtlInitUnicodeString` at `0x18000959d`
- `ntdll!RtlInitUnicodeString` at `0x1800095b8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800097a4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800097a4`
- `RPCRT4!RpcImpersonateClient` at `0x1800095e4`
- `RPCRT4!RpcImpersonateClient` at `0x1800095e4`
- `RPCRT4!RpcRevertToSelf` at `0x18000965b`
- `RPCRT4!RpcRevertToSelf` at `0x18000965b`
- `SspiCli!LsaCallAuthenticationPackage` at `0x180009704`
- `SspiCli!LsaCallAuthenticationPackage` at `0x180009704`
- `SspiCli!LsaFreeReturnBuffer` at `0x180009739`
- `SspiCli!LsaFreeReturnBuffer` at `0x180009739`

## string_xrefs

- `0x18000958e`: `WkstaConfigurationInfo`

## pseudocode

```c
__int64 __fastcall NetrWkstaGetInfo(__int64 a1, int a2, _QWORD *a3)
{
  int v5; // r14d
  ACCESS_MASK DesiredAccess; // edi
  PSECURITY_DESCRIPTOR SecurityDescriptor; // rsi
  NTSTATUS v8; // edi
  _DWORD *v9; // rsi
  unsigned int v10; // eax
  unsigned int v11; // edi
  unsigned int v12; // ecx
  unsigned int v13; // eax
  __int64 v14; // r12
  _DWORD *v15; // rax
  unsigned __int64 v16; // r13
  _WORD *v17; // rdi
  __int64 v18; // rdx
  __int64 v19; // rbx
  __int64 v20; // rdx
  _WORD *v21; // rbx
  __int64 v22; // rdi
  unsigned int PlatformInfo; // edi
  int v24; // ebx
  _WORD *v25; // rcx
  DWORD ReturnBufferLength; // [rsp+60h] [rbp-88h] BYREF
  PVOID ProtocolReturnBuffer; // [rsp+68h] [rbp-80h] BYREF
  int v29; // [rsp+70h] [rbp-78h]
  _WORD *v30; // [rsp+78h] [rbp-70h]
  struct _UNICODE_STRING ObjectName; // [rsp+80h] [rbp-68h] BYREF
  struct _UNICODE_STRING ObjectTypeName; // [rsp+90h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-48h] BYREF
  HLOCAL v34; // [rsp+B0h] [rbp-38h]
  int OldValue; // [rsp+F8h] [rbp+10h] BYREF
  unsigned int GenerateOnClose; // [rsp+108h] [rbp+20h] BYREF

  switch ( a2 )
  {
    case 100:
      v5 = 1;
      DesiredAccess = 1;
      break;
    case 101:
      DesiredAccess = 2;
      v5 = 1;
      break;
    case 102:
    case 502:
      DesiredAccess = 4;
      v5 = 1;
      break;
    default:
      return 124;
  }
  SecurityDescriptor = ConfigurationInfoSd;
  LOBYTE(OldValue) = 0;
  DestinationString = 0;
  ObjectTypeName = 0;
  ObjectName = 0;
  ReturnBufferLength = 0;
  LOBYTE(GenerateOnClose) = 0;
  LODWORD(ProtocolReturnBuffer) = 0;
  RtlInitUnicodeString(&DestinationString, L"Workstation");
  RtlInitUnicodeString(&ObjectTypeName, L"WkstaConfigurationInfo");
  RtlInitUnicodeString(&ObjectName, L"-");
  RtlAdjustPrivilege(0x15u, 1u, 0, (PBOOLEAN)&OldValue);
  if ( RpcImpersonateClient(0) )
    return 5;
  v8 = NtAccessCheckAndAuditAlarm(
         &DestinationString,
         0,
         &ObjectTypeName,
         &ObjectName,
         SecurityDescriptor,
         DesiredAccess,
         &WsConfigInfoMapping,
         0,
         &ReturnBufferLength,
         (PNTSTATUS)&ProtocolReturnBuffer,
         (PBOOLEAN)&GenerateOnClose);
  RpcRevertToSelf();
  if ( v8 < 0 || (_DWORD)ProtocolReturnBuffer )
    return 5;
  v9 = 0;
  if ( RtlAcquireResourceShared(&WsInfo, 1u) )
  {
    if ( a2 == 102 )
    {
      ProtocolReturnBuffer = 0;
      GenerateOnClose = 0;
      ReturnBufferLength = 0;
      OldValue = 2;
      v10 = LsaCallAuthenticationPackage(
              LsaHandle,
              AuthenticationPackage,
              &OldValue,
              4u,
              &ProtocolReturnBuffer,
              &ReturnBufferLength,
              (PNTSTATUS)&GenerateOnClose);
      if ( v10 || (v10 = GenerateOnClose) != 0 )
      {
        PlatformInfo = WsMapStatus(v10);
        if ( PlatformInfo )
          goto LABEL_28;
      }
      if ( !ProtocolReturnBuffer )
      {
        PlatformInfo = 31;
        goto LABEL_28;
      }
      v5 = *((_DWORD *)ProtocolReturnBuffer + 1);
      LsaFreeReturnBuffer(ProtocolReturnBuffer);
    }
    else if ( a2 != 100 && a2 != 101 )
    {
      if ( a2 == 502 )
      {
        PlatformInfo = WsGetPlatformInfo(502, a3);
        v29 = PlatformInfo;
      }
      else
      {
        PlatformInfo = 124;
        v29 = 124;
      }
      goto LABEL_50;
    }
    v30 = 0;
    v11 = 48;
    if ( a2 != 102 )
      v11 = 40;
    if ( (unsigned int)(2 * (dword_180051F4C + dword_180051F70)) >> 1 < dword_180051F4C )
    {
      PlatformInfo = 8;
    }
    else
    {
      v12 = 2 * (dword_180051F4C + dword_180051F70) + 6;
      if ( v12 < 6 )
      {
        PlatformInfo = 8;
      }
      else
      {
        v13 = v11 + v12;
        if ( v11 + v12 < v11 )
        {
          PlatformInfo = 8;
        }
        else
        {
          v14 = v13;
          v15 = LocalAlloc(0x40u, v13);
          v9 = v15;
          v34 = v15;
          if ( v15 )
          {
            memset_0(v15, 0, (unsigned int)v14);
            v16 = (unsigned __int64)&v9[v11 / 4];
            v17 = (_WORD *)((char *)v9 + v14);
            v30 = (_WORD *)((char *)v9 + v14);
            if ( a2 != 100 )
            {
              v24 = a2 - 101;
              if ( v24 )
              {
                if ( v24 != 1 )
                {
LABEL_27:
                  PlatformInfo = 0;
                  goto LABEL_28;
                }
                v9[10] = v5;
              }
              v25 = v17 - 1;
              if ( (unsigned __int64)(v17 - 1) < v16 )
              {
                *((_QWORD *)v9 + 4) = 0;
              }
              else
              {
                --v17;
                v30 = v25;
                *v25 = 0;
                *((_QWORD *)v9 + 4) = v25;
              }
            }
            *v9 = dword_180051F74;
            v9[6] = dword_180051F78;
            v9[7] = dword_180051F7C;
            v18 = (unsigned int)(dword_180051F4C + 1);
            if ( (unsigned __int64)&v17[-v18] < v16 )
            {
              *((_QWORD *)v9 + 1) = 0;
            }
            else
            {
              v17 -= (unsigned int)v18;
              v30 = v17;
              v19 = (unsigned int)dword_180051F4C;
              if ( dword_180051F4C )
                o_wcsncpy_s_0(v17, v18, qword_180051D40, (unsigned int)dword_180051F4C);
              v17[v19] = 0;
              *((_QWORD *)v9 + 1) = v17;
            }
            v20 = (unsigned int)(dword_180051F70 + 1);
            if ( (unsigned __int64)&v17[-v20] < v16 )
            {
              *((_QWORD *)v9 + 2) = 0;
            }
            else
            {
              v21 = &v17[-(unsigned int)v20];
              v30 = v21;
              v22 = (unsigned int)dword_180051F70;
              if ( dword_180051F70 )
                o_wcsncpy_s_0(v21, v20, &word_180051F50, (unsigned int)dword_180051F70);
              v21[v22] = 0;
              *((_QWORD *)v9 + 2) = v21;
            }
            goto LABEL_27;
          }
          PlatformInfo = 8;
        }
      }
    }
LABEL_28:
    v29 = PlatformInfo;
    if ( !PlatformInfo )
      *a3 = v9;
LABEL_50:
    RtlReleaseResource(&WsInfo);
    return PlatformInfo;
  }
  return 2140;
}

```

## disassembly

```asm
0x180009500  mov     [rsp+arg_0], rbx
0x180009505  mov     [rsp+arg_10], rsi
0x18000950a  push    rdi
0x18000950b  push    r12
0x18000950d  push    r13
0x18000950f  push    r14
0x180009511  push    r15
0x180009513  sub     rsp, 0C0h
0x18000951a  mov     r15, r8
0x18000951d  mov     ebx, edx
0x18000951f  cmp     edx, 64h ; 'd'
0x180009522  jnz     loc_1800099D0
0x180009528  mov     r14d, 1
0x18000952e  mov     edi, r14d
0x180009531  mov     rsi, cs:ConfigurationInfoSd
0x180009538  mov     byte ptr [rsp+0E8h+OldValue], 0
0x180009540  xorps   xmm0, xmm0
0x180009543  movups  xmmword ptr [rsp+0E8h+DestinationString.Length], xmm0
0x18000954b  xorps   xmm1, xmm1
0x18000954e  movups  xmmword ptr [rsp+0E8h+ObjectTypeName.Length], xmm1
0x180009556  movups  xmmword ptr [rsp+0E8h+ObjectName.Length], xmm0
0x18000955e  xor     r12d, r12d
0x180009561  mov     [rsp+0E8h+ReturnBufferLength], r12d
0x180009566  mov     byte ptr [rsp+0E8h+arg_18], r12b
0x18000956e  mov     dword ptr [rsp+0E8h+ProtocolReturnBuffer], r12d
0x180009573  lea     rdx, SourceName; "Workstation"
0x18000957a  lea     rcx, [rsp+0E8h+DestinationString]; DestinationString
0x180009582  call    cs:__imp_RtlInitUnicodeString
0x180009589  nop     dword ptr [rax+rax+00h]
0x18000958e  lea     rdx, aWkstaconfigura; "WkstaConfigurationInfo"
0x180009595  lea     rcx, [rsp+0E8h+ObjectTypeName]; DestinationString
0x18000959d  call    cs:__imp_RtlInitUnicodeString
0x1800095a4  nop     dword ptr [rax+rax+00h]
0x1800095a9  lea     rdx, asc_18003DB90; "-"
0x1800095b0  lea     rcx, [rsp+0E8h+ObjectName]; DestinationString
0x1800095b8  call    cs:__imp_RtlInitUnicodeString
0x1800095bf  nop     dword ptr [rax+rax+00h]
0x1800095c4  lea     r9, [rsp+0E8h+OldValue]; OldValue
0x1800095cc  xor     r8d, r8d; ForThread
0x1800095cf  mov     dl, 1; NewValue
0x1800095d1  mov     ecx, 15h; Privilege
0x1800095d6  call    cs:__imp_RtlAdjustPrivilege
0x1800095dd  nop     dword ptr [rax+rax+00h]
0x1800095e2  xor     ecx, ecx; BindingHandle
0x1800095e4  call    cs:__imp_RpcImpersonateClient
0x1800095eb  nop     dword ptr [rax+rax+00h]
0x1800095f0  test    eax, eax
0x1800095f2  jnz     loc_1800099F3
0x1800095f8  lea     rax, [rsp+0E8h+arg_18]
0x180009600  mov     [rsp+0E8h+GenerateOnClose], rax; GenerateOnClose
0x180009605  lea     rax, [rsp+0E8h+ProtocolReturnBuffer]
0x18000960a  mov     [rsp+0E8h+AccessStatus], rax; AccessStatus
0x18000960f  lea     rax, [rsp+0E8h+ReturnBufferLength]
0x180009614  mov     [rsp+0E8h+GrantedAccess], rax; GrantedAccess
0x180009619  mov     [rsp+0E8h+ObjectCreation], r12b; ObjectCreation
0x18000961e  lea     rax, WsConfigInfoMapping
0x180009625  mov     [rsp+0E8h+GenericMapping], rax; GenericMapping
0x18000962a  mov     [rsp+0E8h+DesiredAccess], edi; DesiredAccess
0x18000962e  mov     [rsp+0E8h+SecurityDescriptor], rsi; SecurityDescriptor
0x180009633  lea     r9, [rsp+0E8h+ObjectName]; ObjectName
0x18000963b  lea     r8, [rsp+0E8h+ObjectTypeName]; ObjectTypeName
0x180009643  xor     edx, edx; HandleId
0x180009645  lea     rcx, [rsp+0E8h+DestinationString]; SubsystemName
0x18000964d  call    cs:__imp_NtAccessCheckAndAuditAlarm
0x180009654  nop     dword ptr [rax+rax+00h]
0x180009659  mov     edi, eax
0x18000965b  call    cs:__imp_RpcRevertToSelf
0x180009662  nop     dword ptr [rax+rax+00h]
0x180009667  test    edi, edi
0x180009669  js      loc_1800099F3
0x18000966f  cmp     dword ptr [rsp+0E8h+ProtocolReturnBuffer], r12d
0x180009674  jnz     loc_1800099F3
0x18000967a  mov     esi, r12d
0x18000967d  mov     dl, 1; Wait
0x18000967f  lea     rcx, WsInfo; Resource
0x180009686  call    cs:__imp_RtlAcquireResourceShared
0x18000968d  nop     dword ptr [rax+rax+00h]
0x180009692  test    al, al
0x180009694  jz      loc_180009A01
0x18000969a  cmp     ebx, 66h ; 'f'
0x18000969d  jnz     loc_180009911
0x1800096a3  mov     [rsp+0E8h+ProtocolReturnBuffer], r12
0x1800096a8  mov     [rsp+0E8h+arg_18], r12d
0x1800096b0  mov     [rsp+0E8h+OldValue], r12d
0x1800096b8  mov     [rsp+0E8h+ReturnBufferLength], r12d
0x1800096bd  mov     [rsp+0E8h+OldValue], 2
0x1800096c8  lea     rax, [rsp+0E8h+arg_18]
0x1800096d0  mov     [rsp+0E8h+GenericMapping], rax; ProtocolStatus
0x1800096d5  lea     rax, [rsp+0E8h+ReturnBufferLength]
0x1800096da  mov     qword ptr [rsp+0E8h+DesiredAccess], rax; ReturnBufferLength
0x1800096df  lea     rax, [rsp+0E8h+ProtocolReturnBuffer]
0x1800096e4  mov     [rsp+0E8h+SecurityDescriptor], rax; ProtocolReturnBuffer
0x1800096e9  mov     r9d, 4; SubmitBufferLength
0x1800096ef  lea     r8, [rsp+0E8h+OldValue]; ProtocolSubmitBuffer
0x1800096f7  mov     edx, cs:AuthenticationPackage; AuthenticationPackage
0x1800096fd  mov     rcx, cs:LsaHandle; LsaHandle
0x180009704  call    cs:__imp_LsaCallAuthenticationPackage
0x18000970b  nop     dword ptr [rax+rax+00h]
0x180009710  test    eax, eax
0x180009712  jnz     loc_18000994C
0x180009718  mov     eax, [rsp+0E8h+arg_18]
0x18000971f  test    eax, eax
0x180009721  jnz     loc_18000994C
0x180009727  mov     rcx, [rsp+0E8h+ProtocolReturnBuffer]; Buffer
0x18000972c  test    rcx, rcx
0x18000972f  jz      loc_180009962
0x180009735  mov     r14d, [rcx+4]
0x180009739  call    cs:__imp_LsaFreeReturnBuffer
0x180009740  nop     dword ptr [rax+rax+00h]
0x180009745  jmp     short loc_180009750
0x180009747  cmp     ebx, 66h ; 'f'
0x18000974a  jz      loc_1800096A3
0x180009750  mov     [rsp+0E8h+var_70], r12
0x180009755  mov     edi, 30h ; '0'
0x18000975a  mov     eax, 28h ; '('
0x18000975f  cmp     ebx, 66h ; 'f'
0x180009762  cmovnz  edi, eax
0x180009765  mov     ecx, cs:dword_180051F70
0x18000976b  add     ecx, cs:dword_180051F4C
0x180009771  add     ecx, ecx
0x180009773  mov     eax, ecx
0x180009775  shr     eax, 1
0x180009777  cmp     eax, cs:dword_180051F4C
0x18000977d  jb      loc_1800098AB
0x180009783  add     ecx, 6
0x180009786  cmp     ecx, 6
0x180009789  jb      loc_18000996C
0x18000978f  lea     eax, [rdi+rcx]
0x180009792  cmp     eax, edi
0x180009794  jb      loc_1800098FD
0x18000979a  mov     r12d, eax
0x18000979d  mov     edx, eax; uBytes
0x18000979f  mov     ecx, 40h ; '@'; uFlags
0x1800097a4  call    cs:__imp_LocalAlloc
0x1800097ab  nop     dword ptr [rax+rax+00h]
0x1800097b0  mov     rsi, rax
0x1800097b3  mov     [rsp+0E8h+var_38], rax
0x1800097bb  test    rax, rax
0x1800097be  jz      loc_1800098DF
0x1800097c4  mov     r8d, r12d; Size
0x1800097c7  xor     edx, edx; Val
0x1800097c9  mov     rcx, rax; void *
0x1800097cc  call    memset_0
0x1800097d1  mov     r13d, edi
0x1800097d4  add     r13, rsi
0x1800097d7  lea     rdi, [r12+rsi]
0x1800097db  mov     [rsp+0E8h+var_70], rdi
0x1800097e0  cmp     ebx, 64h ; 'd'
0x1800097e3  jnz     loc_1800098B2
0x1800097e9  mov     eax, cs:dword_180051F74
0x1800097ef  mov     [rsi], eax
0x1800097f1  mov     eax, cs:dword_180051F78
0x1800097f7  mov     [rsi+18h], eax
0x1800097fa  mov     eax, cs:dword_180051F7C
0x180009800  mov     [rsi+1Ch], eax
0x180009803  mov     ecx, cs:dword_180051F4C
0x180009809  lea     edx, [rcx+1]
0x18000980c  imul    rax, rdx, -2
0x180009810  add     rax, rdi
0x180009813  cmp     rax, r13
0x180009816  jb      loc_1800098E6
0x18000981c  mov     eax, edx
0x18000981e  neg     rax
0x180009821  lea     rdi, [rdi+rax*2]
0x180009825  mov     [rsp+0E8h+var_70], rdi
0x18000982a  mov     ebx, ecx
0x18000982c  test    ecx, ecx
0x18000982e  jz      short loc_180009842
0x180009830  mov     r9d, ecx
0x180009833  lea     r8, qword_180051D40
0x18000983a  mov     rcx, rdi
0x18000983d  call    _o_wcsncpy_s_0
0x180009842  xor     eax, eax
0x180009844  mov     [rdi+rbx*2], ax
0x180009848  mov     [rsi+8], rdi
0x18000984c  mov     ecx, cs:dword_180051F70
0x180009852  lea     edx, [rcx+1]
0x180009855  imul    rax, rdx, -2
0x180009859  add     rax, rdi
0x18000985c  cmp     rax, r13
0x18000985f  jb      loc_1800098F3
0x180009865  mov     eax, edx
0x180009867  neg     rax
0x18000986a  lea     rbx, [rdi+rax*2]
0x18000986e  mov     [rsp+0E8h+var_70], rbx
0x180009873  mov     edi, ecx
0x180009875  test    ecx, ecx
0x180009877  jz      short loc_18000988B
0x180009879  mov     r9d, ecx
0x18000987c  lea     r8, word_180051F50
0x180009883  mov     rcx, rbx
0x180009886  call    _o_wcsncpy_s_0
0x18000988b  xor     eax, eax
0x18000988d  mov     [rbx+rdi*2], ax
0x180009891  mov     [rsi+10h], rbx
0x180009895  xor     edi, edi
0x180009897  mov     [rsp+0E8h+var_78], edi
0x18000989b  test    edi, edi
0x18000989d  jnz     loc_180009976
0x1800098a3  mov     [r15], rsi
0x1800098a6  jmp     loc_180009976
0x1800098ab  mov     edi, 8
0x1800098b0  jmp     short loc_180009897
0x1800098b2  sub     ebx, 65h ; 'e'
0x1800098b5  jz      short loc_1800098C0
0x1800098b7  cmp     ebx, 1
0x1800098ba  jnz     short loc_180009895
0x1800098bc  mov     [rsi+28h], r14d
0x1800098c0  lea     rcx, [rdi-2]
0x1800098c4  cmp     rcx, r13
0x1800098c7  jb      short loc_180009904
0x1800098c9  mov     rdi, rcx
0x1800098cc  mov     [rsp+0E8h+var_70], rcx
0x1800098d1  xor     eax, eax
0x1800098d3  mov     [rcx], ax
0x1800098d6  mov     [rsi+20h], rcx
0x1800098da  jmp     loc_1800097E9
0x1800098df  mov     edi, 8
0x1800098e4  jmp     short loc_180009897
0x1800098e6  mov     qword ptr [rsi+8], 0
0x1800098ee  jmp     loc_18000984C
0x1800098f3  mov     qword ptr [rsi+10h], 0
0x1800098fb  jmp     short loc_180009895
0x1800098fd  mov     edi, 8
0x180009902  jmp     short loc_180009897
0x180009904  mov     qword ptr [rsi+20h], 0
0x18000990c  jmp     loc_1800097E9
0x180009911  mov     eax, ebx
0x180009913  sub     eax, 64h ; 'd'
0x180009916  jz      loc_180009747
0x18000991c  sub     eax, 1
0x18000991f  jz      loc_180009747
0x180009925  cmp     eax, 191h
0x18000992a  jz      short loc_180009937
0x18000992c  mov     edi, 7Ch ; '|'
0x180009931  mov     [rsp+0E8h+var_78], edi
0x180009935  jmp     short loc_180009976
0x180009937  mov     rdx, r15
0x18000993a  mov     ecx, 1F6h
0x18000993f  call    WsGetPlatformInfo
0x180009944  mov     edi, eax
0x180009946  mov     [rsp+0E8h+var_78], eax
0x18000994a  jmp     short loc_180009976
0x18000994c  mov     ecx, eax
0x18000994e  call    WsMapStatus
0x180009953  mov     edi, eax
0x180009955  test    eax, eax
0x180009957  jnz     loc_180009897
0x18000995d  jmp     loc_180009727
0x180009962  mov     edi, 1Fh
0x180009967  jmp     loc_180009897
0x18000996c  mov     edi, 8
0x180009971  jmp     loc_180009897
0x180009976  jmp     short loc_18000999D
0x180009978  mov     ebx, eax
0x18000997a  lea     rcx, WsInfo; Resource
0x180009981  call    cs:__imp_RtlReleaseResource
0x180009988  nop     dword ptr [rax+rax+00h]
0x18000998d  mov     ecx, ebx; Status
0x18000998f  call    cs:__imp_RtlNtStatusToDosError
0x180009996  nop     dword ptr [rax+rax+00h]
0x18000999b  jmp     short loc_1800099B2
0x18000999d  lea     rcx, WsInfo; Resource
0x1800099a4  call    cs:__imp_RtlReleaseResource
0x1800099ab  nop     dword ptr [rax+rax+00h]
0x1800099b0  mov     eax, edi
0x1800099b2  lea     r11, [rsp+0E8h+var_28]
0x1800099ba  mov     rbx, [r11+30h]
0x1800099be  mov     rsi, [r11+40h]
0x1800099c2  mov     rsp, r11
0x1800099c5  pop     r15
0x1800099c7  pop     r14
0x1800099c9  pop     r13
0x1800099cb  pop     r12
0x1800099cd  pop     rdi
0x1800099ce  retn
0x1800099d0  mov     eax, ebx
0x1800099d2  sub     eax, 65h ; 'e'
0x1800099d5  jz      short loc_180009A08
0x1800099d7  sub     eax, 1
0x1800099da  jz      short loc_1800099E3
0x1800099dc  cmp     eax, 190h
0x1800099e1  jnz     short loc_1800099FA
0x1800099e3  mov     edi, 4
0x1800099e8  mov     r14d, 1
0x1800099ee  jmp     loc_180009531
0x1800099f3  mov     eax, 5
0x1800099f8  jmp     short loc_1800099B2
0x1800099fa  mov     eax, 7Ch ; '|'
0x1800099ff  jmp     short loc_1800099B2
0x180009a01  mov     eax, 85Ch
0x180009a06  jmp     short loc_1800099B2
0x180009a08  mov     edi, 2
0x180009a0d  mov     r14d, 1
0x180009a13  jmp     loc_180009531
```
