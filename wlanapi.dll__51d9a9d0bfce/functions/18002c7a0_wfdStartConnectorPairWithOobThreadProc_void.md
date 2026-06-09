# wfdStartConnectorPairWithOobThreadProc(void *)

- ea: `0x18002c7a0`
- end: `0x18002cc03`
- name: `?wfdStartConnectorPairWithOobThreadProc@@YAKPEAX@Z`
- size: `1123`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005610`
- `0x180019a20`
- `0x18002c7a0`
- `0x180038fa8`
- `0x180055a38`
- `0x180055d20`
- `0x1800560cc`
- `0x180056280`
- `0x1800572d4`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c870`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c8fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c9e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002caab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002cb26`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002cbb7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c870`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c8fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c9e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002caab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002cb26`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002cbb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c8dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c939`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ca58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cb04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cb6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cbee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c8dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c939`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ca58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cb04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cb6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cbee`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c8f0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c8f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c91f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c91f`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18002c9b0`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18002c9b0`

## pseudocode

```c
__int64 __fastcall wfdStartConnectorPairWithOobThreadProc(_QWORD *Parameter)
{
  int v2; // ecx
  int v3; // esi
  void *v4; // r14
  int v5; // ecx
  unsigned int LastError; // edi
  void *v7; // rcx
  DWORD v8; // edi
  char *v9; // rdx
  void **v11; // rsi
  void *v12; // rcx
  unsigned int v13; // r9d
  int v14; // edx
  int v15; // r8d
  int v16; // ecx
  int v17; // eax
  int v18; // [rsp+40h] [rbp-69h]
  void *v19; // [rsp+48h] [rbp-61h]
  unsigned int v20; // [rsp+50h] [rbp-59h] BYREF
  int v21; // [rsp+54h] [rbp-55h] BYREF
  unsigned int v22; // [rsp+58h] [rbp-51h]
  unsigned __int16 *v23; // [rsp+60h] [rbp-49h] BYREF
  struct _WFD_VERTICAL_PAIRING_INFO *v24; // [rsp+68h] [rbp-41h] BYREF
  int v25; // [rsp+70h] [rbp-39h] BYREF
  char v26[14]; // [rsp+74h] [rbp-35h] BYREF
  __int128 v27; // [rsp+82h] [rbp-27h]
  int v28; // [rsp+92h] [rbp-17h]
  __int16 v29; // [rsp+96h] [rbp-13h]
  int v30; // [rsp+98h] [rbp-11h]
  __int128 v31; // [rsp+9Ch] [rbp-Dh]
  __int128 v32; // [rsp+ACh] [rbp+3h]
  __int64 v33; // [rsp+BCh] [rbp+13h]
  char v34; // [rsp+C4h] [rbp+1Bh]
  __int16 v35; // [rsp+C5h] [rbp+1Ch]
  char v36; // [rsp+C7h] [rbp+1Eh]
  int v37; // [rsp+C8h] [rbp+1Fh]

  v2 = *((_DWORD *)Parameter + 233);
  v3 = 0;
  v4 = 0;
  strcpy(v26, "PROXIMITY_OOB");
  v25 = 6029569;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v33 = 257;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v21 = 0;
  v20 = 0;
  v24 = 0;
  v23 = 0;
  v18 = 0;
  v19 = 0;
  v27 = 0;
  v31 = 0;
  v32 = 0;
  v5 = v2 - 1;
  if ( !v5 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 1));
    v11 = (void **)(Parameter + 115);
    if ( (Parameter[116] & 0x20000) != 0 )
    {
      LastError = 1223;
    }
    else
    {
      v12 = (void *)Parameter[7];
      *((_DWORD *)Parameter + 232) = 2;
      LastError = WFDPairEnumerateCeremoniesLib(
                    v12,
                    (unsigned __int8 (*)[6])((unsigned __int8 *)Parameter + 88),
                    (struct _WFD_PAIRING_PARAMETERS *)&v25,
                    0,
                    (void **)Parameter + 115,
                    (enum _DOT11_WPS_CONFIG_METHOD *)&v21,
                    &v20);
      if ( LastError )
        *((_DWORD *)Parameter + 232) = 524298;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(Parameter + 1));
    v13 = *((_DWORD *)Parameter + 173);
    v14 = (v13 >> 5) & 8 | 0x100;
    if ( (v13 & 8) == 0 )
      v14 = (*((_DWORD *)Parameter + 173) >> 5) & 8;
    v15 = v14 | 0x80;
    if ( (v13 & 0x80u) == 0 )
      v15 = v14;
    v16 = v15 | 0x40;
    if ( (v13 & 0x40) == 0 )
      v16 = v15;
    v17 = v16 | 0x40;
    if ( (v13 & 0x20) == 0 )
      v17 = v16;
    v22 = v17;
    EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 1));
    if ( LastError )
    {
      *((_DWORD *)Parameter + 232) = 524298;
    }
    else
    {
      if ( (v22 & v21) != 0 )
      {
        if ( (Parameter[116] & 0x20000) == 0 )
        {
          *((_DWORD *)Parameter + 232) = 65539;
LABEL_48:
          LeaveCriticalSection((LPCRITICAL_SECTION)(Parameter + 1));
          if ( LastError )
          {
LABEL_62:
            v3 = v18;
            v4 = v19;
            goto LABEL_16;
          }
          LastError = WFDPairSelectCeremonyLib(*v11, v22, &v20);
          EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 1));
          if ( LastError )
          {
            *((_DWORD *)Parameter + 232) = 524298;
          }
          else
          {
            if ( (Parameter[116] & 0x20000) == 0 )
            {
              *((_DWORD *)Parameter + 232) = 65540;
LABEL_55:
              LeaveCriticalSection((LPCRITICAL_SECTION)(Parameter + 1));
              if ( !LastError )
              {
                LastError = WFDPairWithDeviceAndOpenSessionLib(
                              *v11,
                              (struct _WFD_WPS_INFO *)(Parameter + 87),
                              0,
                              &v23,
                              &v24,
                              &v20,
                              (struct _GUID *)(Parameter + 117),
                              0);
                EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 1));
                if ( LastError )
                {
                  *((_DWORD *)Parameter + 232) = 524298;
                  *v11 = 0;
                }
                else if ( (Parameter[116] & 0x20000) != 0 )
                {
                  LastError = 1223;
                }
                else
                {
                  *((_DWORD *)Parameter + 232) = 262151;
                }
                LeaveCriticalSection((LPCRITICAL_SECTION)(Parameter + 1));
              }
              goto LABEL_62;
            }
            LastError = 1223;
            v19 = *v11;
            v18 = 1;
          }
          *v11 = 0;
          goto LABEL_55;
        }
        LastError = 1223;
      }
      else
      {
        LastError = 13;
        *((_DWORD *)Parameter + 232) = 524298;
      }
      v19 = *v11;
      v18 = 1;
    }
    *v11 = 0;
    goto LABEL_48;
  }
  if ( v5 == 1 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 1));
    if ( (Parameter[116] & 0x20000) != 0 )
    {
      LastError = 1223;
    }
    else
    {
      v7 = (void *)Parameter[7];
      *((_DWORD *)Parameter + 232) = 65542;
      LastError = WFDStartOpenSessionLib(
                    v7,
                    (unsigned __int8 (*)[6])((unsigned __int8 *)Parameter + 88),
                    Parameter,
                    (void (*)(void *, void *, struct _GUID *__struct_ptr, unsigned int, unsigned int))wfdConnectorOnOpenSessionComplete,
                    0,
                    0,
                    (void **)Parameter + 115);
      if ( LastError )
        *((_DWORD *)Parameter + 232) = 524298;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(Parameter + 1));
    if ( !LastError )
    {
      v8 = WaitForSingleObject((HANDLE)Parameter[122], 0xFFFFFFFF);
      EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 1));
      if ( (Parameter[116] & 0x20000) != 0 )
      {
        LastError = 1223;
        *((_DWORD *)Parameter + 232) = 524297;
      }
      else if ( v8 )
      {
        LastError = GetLastError();
        *((_DWORD *)Parameter + 232) = 524298;
      }
      else
      {
        LastError = *((_DWORD *)Parameter + 238);
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(Parameter + 1));
    }
    v3 = 0;
    v4 = 0;
  }
  else
  {
    LastError = 5023;
  }
LABEL_16:
  v9 = (char *)(Parameter + 117);
  if ( LastError )
    v9 = 0;
  ((void (__fastcall *)(_QWORD, char *, _QWORD, _QWORD))Parameter[10])(*Parameter, v9, Parameter[11], LastError);
  if ( *((_DWORD *)Parameter + 17) )
    WFDOobHelperSetPCDiscoverable(0, (struct _WFD_OOB_SESSION_CONTEXT *)Parameter);
  if ( v3 )
    WFDPairCancelLib(v4);
  if ( v23 )
    FreeWLMem(v23);
  if ( v24 )
    FreeWLMem(v24);
  HtDereferenceHandleWithTag(g_hHandleTable, *Parameter, 0, 1);
  return LastError;
}

```

## disassembly

```asm
0x18002c7a0  mov     [rsp-8+arg_8], rbx
0x18002c7a5  mov     [rsp-8+arg_10], rsi
0x18002c7aa  push    rbp
0x18002c7ab  push    rdi
0x18002c7ac  push    r12
0x18002c7ae  push    r13
0x18002c7b0  push    r14
0x18002c7b2  lea     rbp, [rsp-37h]
0x18002c7b7  sub     rsp, 0E0h
0x18002c7be  mov     rax, cs:__security_cookie
0x18002c7c5  xor     rax, rsp
0x18002c7c8  mov     [rbp+57h+var_30], rax
0x18002c7cc  mov     eax, dword ptr cs:aProximityOob+8; "Y_OOB"
0x18002c7d2  xor     r13d, r13d
0x18002c7d5  movsd   xmm0, qword ptr cs:aProximityOob; "PROXIMITY_OOB"
0x18002c7dd  mov     rbx, rcx
0x18002c7e0  mov     ecx, [rcx+3A4h]
0x18002c7e6  mov     esi, r13d
0x18002c7e9  mov     dword ptr [rbp+57h+var_8C+8], eax
0x18002c7ec  mov     r14d, r13d
0x18002c7ef  movzx   eax, word ptr cs:aProximityOob+0Ch; "B"
0x18002c7f6  mov     word ptr [rbp+57h+var_8C+0Ch], ax
0x18002c7fa  xor     eax, eax
0x18002c7fc  movsd   qword ptr [rbp+57h+var_8C], xmm0
0x18002c801  xorps   xmm0, xmm0
0x18002c804  mov     [rbp+57h+var_90], 5C0101h
0x18002c80b  mov     [rbp+57h+var_6E], eax
0x18002c80e  mov     [rbp+57h+var_6A], ax
0x18002c812  mov     [rbp+57h+var_68], r13d
0x18002c816  mov     [rbp+57h+var_44], 101h
0x18002c81e  mov     [rbp+57h+var_3C], r13b
0x18002c822  mov     [rbp+57h+var_3B], ax
0x18002c826  mov     [rbp+57h+var_39], al
0x18002c829  mov     [rbp+57h+var_38], r13d
0x18002c82d  mov     [rbp+57h+var_AC], r13d
0x18002c831  mov     [rbp+57h+var_B0], r13d
0x18002c835  mov     [rbp+57h+var_98], r13
0x18002c839  mov     [rbp+57h+var_A0], r13
0x18002c83d  mov     [rbp+57h+var_C0], r13d
0x18002c841  mov     [rbp+57h+var_B8], r13
0x18002c845  movups  [rbp+57h+var_7E], xmm0
0x18002c849  movups  [rbp+57h+var_64], xmm0
0x18002c84d  movups  [rbp+57h+var_54], xmm0
0x18002c851  sub     ecx, 1
0x18002c854  jz      loc_18002C9E0
0x18002c85a  cmp     ecx, 1
0x18002c85d  jz      short loc_18002C869
0x18002c85f  mov     edi, 139Fh
0x18002c864  jmp     loc_18002C945
0x18002c869  lea     rsi, [rbx+8]
0x18002c86d  mov     rcx, rsi; lpCriticalSection
0x18002c870  call    cs:__imp_EnterCriticalSection
0x18002c876  mov     r12d, 20000h
0x18002c87c  mov     r14d, 8000Ah
0x18002c882  test    [rbx+3A0h], r12d
0x18002c889  jz      short loc_18002C892
0x18002c88b  mov     edi, 4C7h
0x18002c890  jmp     short loc_18002C8D9
0x18002c892  mov     rcx, [rbx+38h]; void *
0x18002c896  lea     rax, [rbx+398h]
0x18002c89d  mov     [rsp+100h+var_D0], rax; void **
0x18002c8a2  lea     rdx, [rbx+210h]; unsigned __int8 (*)[6]
0x18002c8a9  mov     [rsp+100h+var_D8], r13; struct _WFD_FIREWALL_CONFIGURATION_PARAMETERS *
0x18002c8ae  lea     r9, ?wfdConnectorOnOpenSessionComplete@@YAXPEAX0U_GUID@@KK@Z; void (*)(void *, void *, struct _GUID *__struct_ptr, unsigned int, unsigned int)
0x18002c8b5  mov     r8, rbx; void *
0x18002c8b8  mov     [rsp+100h+var_E0], r13; unsigned __int16 *
0x18002c8bd  mov     dword ptr [rbx+3A0h], 10006h
0x18002c8c7  call    ?WFDStartOpenSessionLib@@YAKPEAXPEAY05E0P6AX00U_GUID@@KK@ZPEAGPEBU_WFD_FIREWALL_CONFIGURATION_PARAMETERS@@PEAPEAX@Z; WFDStartOpenSessionLib(void *,uchar (*)[6],void *,void (*)(void *,void *,_GUID,ulong,ulong),ushort *,_WFD_FIREWALL_CONFIGURATION_PARAMETERS const *,void * *)
0x18002c8cc  mov     edi, eax
0x18002c8ce  test    eax, eax
0x18002c8d0  jz      short loc_18002C8D9
0x18002c8d2  mov     [rbx+3A0h], r14d
0x18002c8d9  mov     rcx, rsi; lpCriticalSection
0x18002c8dc  call    cs:__imp_LeaveCriticalSection
0x18002c8e2  test    edi, edi
0x18002c8e4  jnz     short loc_18002C93F
0x18002c8e6  mov     rcx, [rbx+3D0h]; hHandle
0x18002c8ed  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002c8f0  call    cs:__imp_WaitForSingleObject
0x18002c8f6  mov     rcx, rsi; lpCriticalSection
0x18002c8f9  mov     edi, eax
0x18002c8fb  call    cs:__imp_EnterCriticalSection
0x18002c901  test    [rbx+3A0h], r12d
0x18002c908  jz      short loc_18002C91B
0x18002c90a  mov     edi, 4C7h
0x18002c90f  mov     dword ptr [rbx+3A0h], 80009h
0x18002c919  jmp     short loc_18002C936
0x18002c91b  test    edi, edi
0x18002c91d  jz      short loc_18002C930
0x18002c91f  call    cs:__imp_GetLastError
0x18002c925  mov     edi, eax
0x18002c927  mov     [rbx+3A0h], r14d
0x18002c92e  jmp     short loc_18002C936
0x18002c930  mov     edi, [rbx+3B8h]
0x18002c936  mov     rcx, rsi; lpCriticalSection
0x18002c939  call    cs:__imp_LeaveCriticalSection
0x18002c93f  mov     esi, r13d
0x18002c942  mov     r14d, esi
0x18002c945  mov     r8, [rbx+58h]
0x18002c949  lea     rdx, [rbx+3A8h]
0x18002c950  mov     rcx, [rbx]
0x18002c953  test    edi, edi
0x18002c955  mov     rax, [rbx+50h]
0x18002c959  mov     r9d, edi
0x18002c95c  cmovnz  rdx, r13
0x18002c960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c965  cmp     [rbx+44h], r13d
0x18002c969  jz      short loc_18002C975
0x18002c96b  mov     rdx, rbx; struct _WFD_OOB_SESSION_CONTEXT *
0x18002c96e  xor     ecx, ecx; int
0x18002c970  call    ?WFDOobHelperSetPCDiscoverable@@YAKHPEAU_WFD_OOB_SESSION_CONTEXT@@@Z; WFDOobHelperSetPCDiscoverable(int,_WFD_OOB_SESSION_CONTEXT *)
0x18002c975  test    esi, esi
0x18002c977  jz      short loc_18002C981
0x18002c979  mov     rcx, r14; void *
0x18002c97c  call    ?WFDPairCancelLib@@YAKPEAX@Z; WFDPairCancelLib(void *)
0x18002c981  mov     rcx, [rbp+57h+var_A0]
0x18002c985  test    rcx, rcx
0x18002c988  jz      short loc_18002C98F
0x18002c98a  call    FreeWLMem
0x18002c98f  mov     rcx, [rbp+57h+var_98]
0x18002c993  test    rcx, rcx
0x18002c996  jz      short loc_18002C99D
0x18002c998  call    FreeWLMem
0x18002c99d  mov     rdx, [rbx]
0x18002c9a0  mov     r9d, 1
0x18002c9a6  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x18002c9ad  xor     r8d, r8d
0x18002c9b0  call    cs:__imp_HtDereferenceHandleWithTag
0x18002c9b6  mov     eax, edi
0x18002c9b8  mov     rcx, [rbp+57h+var_30]
0x18002c9bc  xor     rcx, rsp; StackCookie
0x18002c9bf  call    __security_check_cookie
0x18002c9c4  lea     r11, [rsp+100h+var_20]
0x18002c9cc  mov     rbx, [r11+38h]
0x18002c9d0  mov     rsi, [r11+40h]
0x18002c9d4  mov     rsp, r11
0x18002c9d7  pop     r14
0x18002c9d9  pop     r13
0x18002c9db  pop     r12
0x18002c9dd  pop     rdi
0x18002c9de  pop     rbp
0x18002c9df  retn
0x18002c9e0  lea     r13, [rbx+8]
0x18002c9e4  mov     rcx, r13; lpCriticalSection
0x18002c9e7  call    cs:__imp_EnterCriticalSection
0x18002c9ed  mov     r12d, 20000h
0x18002c9f3  lea     rsi, [rbx+398h]
0x18002c9fa  mov     r14d, 8000Ah
0x18002ca00  test    [rbx+3A0h], r12d
0x18002ca07  jz      short loc_18002CA10
0x18002ca09  mov     edi, 4C7h
0x18002ca0e  jmp     short loc_18002CA55
0x18002ca10  mov     rcx, [rbx+38h]; void *
0x18002ca14  lea     rax, [rbp+57h+var_B0]
0x18002ca18  mov     [rsp+100h+var_D0], rax; unsigned int *
0x18002ca1d  lea     rdx, [rbx+210h]; unsigned __int8 (*)[6]
0x18002ca24  lea     rax, [rbp+57h+var_AC]
0x18002ca28  mov     dword ptr [rbx+3A0h], 2
0x18002ca32  mov     [rsp+100h+var_D8], rax; enum _DOT11_WPS_CONFIG_METHOD *
0x18002ca37  lea     r8, [rbp+57h+var_90]; struct _WFD_PAIRING_PARAMETERS *
0x18002ca3b  xor     r9d, r9d; struct _WFD_FIREWALL_CONFIGURATION_PARAMETERS *
0x18002ca3e  mov     [rsp+100h+var_E0], rsi; void **
0x18002ca43  call    ?WFDPairEnumerateCeremoniesLib@@YAKPEAXPEAY05EPEAU_WFD_PAIRING_PARAMETERS@@PEBU_WFD_FIREWALL_CONFIGURATION_PARAMETERS@@PEAPEAXPEAW4_DOT11_WPS_CONFIG_METHOD@@PEAK@Z; WFDPairEnumerateCeremoniesLib(void *,uchar (*)[6],_WFD_PAIRING_PARAMETERS *,_WFD_FIREWALL_CONFIGURATION_PARAMETERS const *,void * *,_DOT11_WPS_CONFIG_METHOD *,ulong *)
0x18002ca48  mov     edi, eax
0x18002ca4a  test    eax, eax
0x18002ca4c  jz      short loc_18002CA55
0x18002ca4e  mov     [rbx+3A0h], r14d
0x18002ca55  mov     rcx, r13; lpCriticalSection
0x18002ca58  call    cs:__imp_LeaveCriticalSection
0x18002ca5e  mov     r9d, [rbx+2B4h]
0x18002ca65  mov     ecx, r9d
0x18002ca68  shr     ecx, 5
0x18002ca6b  and     ecx, 8
0x18002ca6e  mov     edx, ecx
0x18002ca70  bts     edx, 8
0x18002ca74  test    r9b, 8
0x18002ca78  cmovz   edx, ecx
0x18002ca7b  mov     r8d, edx
0x18002ca7e  bts     r8d, 7
0x18002ca83  test    r9b, 80h
0x18002ca87  cmovz   r8d, edx
0x18002ca8b  mov     ecx, r8d
0x18002ca8e  or      ecx, 40h
0x18002ca91  test    r9b, 40h
0x18002ca95  cmovz   ecx, r8d
0x18002ca99  mov     eax, ecx
0x18002ca9b  or      eax, 40h
0x18002ca9e  test    r9b, 20h
0x18002caa2  cmovz   eax, ecx
0x18002caa5  mov     rcx, r13; lpCriticalSection
0x18002caa8  mov     [rbp+57h+var_A8], eax
0x18002caab  call    cs:__imp_EnterCriticalSection
0x18002cab1  xor     ecx, ecx
0x18002cab3  test    edi, edi
0x18002cab5  jz      short loc_18002CAC3
0x18002cab7  mov     [rbx+3A0h], r14d
0x18002cabe  mov     [rsi], rcx
0x18002cac1  jmp     short loc_18002CB01
0x18002cac3  mov     eax, [rbp+57h+var_A8]
0x18002cac6  test    [rbp+57h+var_AC], eax
0x18002cac9  jnz     short loc_18002CAE7
0x18002cacb  mov     edi, 0Dh
0x18002cad0  mov     [rbx+3A0h], r14d
0x18002cad7  mov     rax, [rsi]
0x18002cada  mov     [rbp+57h+var_B8], rax
0x18002cade  mov     [rbp+57h+var_C0], 1
0x18002cae5  jmp     short loc_18002CABE
0x18002cae7  test    [rbx+3A0h], r12d
0x18002caee  jz      short loc_18002CAF7
0x18002caf0  mov     edi, 4C7h
0x18002caf5  jmp     short loc_18002CAD7
0x18002caf7  mov     dword ptr [rbx+3A0h], 10003h
0x18002cb01  mov     rcx, r13; lpCriticalSection
0x18002cb04  call    cs:__imp_LeaveCriticalSection
0x18002cb0a  test    edi, edi
0x18002cb0c  jnz     loc_18002CBF4
0x18002cb12  mov     edx, [rbp+57h+var_A8]
0x18002cb15  lea     r8, [rbp+57h+var_B0]
0x18002cb19  mov     rcx, [rsi]
0x18002cb1c  call    ?WFDPairSelectCeremonyLib@@YAKPEAXW4_DOT11_WPS_CONFIG_METHOD@@PEAK@Z; WFDPairSelectCeremonyLib(void *,_DOT11_WPS_CONFIG_METHOD,ulong *)
0x18002cb21  mov     rcx, r13; lpCriticalSection
0x18002cb24  mov     edi, eax
0x18002cb26  call    cs:__imp_EnterCriticalSection
0x18002cb2c  test    edi, edi
0x18002cb2e  jz      short loc_18002CB40
0x18002cb30  mov     [rbx+3A0h], r14d
0x18002cb37  mov     qword ptr [rsi], 0
0x18002cb3e  jmp     short loc_18002CB68
0x18002cb40  test    [rbx+3A0h], r12d
0x18002cb47  jz      short loc_18002CB5E
0x18002cb49  mov     rax, [rsi]
0x18002cb4c  mov     edi, 4C7h
0x18002cb51  mov     [rbp+57h+var_B8], rax
0x18002cb55  mov     [rbp+57h+var_C0], 1
0x18002cb5c  jmp     short loc_18002CB37
0x18002cb5e  mov     dword ptr [rbx+3A0h], 10004h
0x18002cb68  mov     rcx, r13; lpCriticalSection
0x18002cb6b  call    cs:__imp_LeaveCriticalSection
0x18002cb71  test    edi, edi
0x18002cb73  jnz     short loc_18002CBF4
0x18002cb75  mov     rcx, [rsi]; void *
0x18002cb78  lea     rax, [rbx+3A8h]
0x18002cb7f  mov     [rsp+100h+var_C8], 0; struct _WFD_PAIRING_AUX_DATA **
0x18002cb88  lea     rdx, [rbx+2B8h]; struct _WFD_WPS_INFO *
0x18002cb8f  mov     [rsp+100h+var_D0], rax; struct _GUID *
0x18002cb94  lea     r9, [rbp+57h+var_A0]; unsigned __int16 **
0x18002cb98  lea     rax, [rbp+57h+var_B0]
0x18002cb9c  xor     r8d, r8d; struct _WFD_VERTICAL_PAIRING_INFO *
0x18002cb9f  mov     [rsp+100h+var_D8], rax; unsigned int *
0x18002cba4  lea     rax, [rbp+57h+var_98]
0x18002cba8  mov     [rsp+100h+var_E0], rax; struct _WFD_VERTICAL_PAIRING_INFO **
0x18002cbad  call    ?WFDPairWithDeviceAndOpenSessionLib@@YAKPEAXPEAU_WFD_WPS_INFO@@PEAU_WFD_VERTICAL_PAIRING_INFO@@PEAPEAGPEAPEAU2@PEAKPEAU_GUID@@PEAPEAU_WFD_PAIRING_AUX_DATA@@@Z; WFDPairWithDeviceAndOpenSessionLib(void *,_WFD_WPS_INFO *,_WFD_VERTICAL_PAIRING_INFO *,ushort * *,_WFD_VERTICAL_PAIRING_INFO * *,ulong *,_GUID *,_WFD_PAIRING_AUX_DATA * *)
0x18002cbb2  mov     rcx, r13; lpCriticalSection
0x18002cbb5  mov     edi, eax
0x18002cbb7  call    cs:__imp_EnterCriticalSection
0x18002cbbd  test    edi, edi
0x18002cbbf  jz      short loc_18002CBD1
0x18002cbc1  mov     [rbx+3A0h], r14d
0x18002cbc8  mov     qword ptr [rsi], 0
0x18002cbcf  jmp     short loc_18002CBEB
0x18002cbd1  test    [rbx+3A0h], r12d
0x18002cbd8  jz      short loc_18002CBE1
0x18002cbda  mov     edi, 4C7h
0x18002cbdf  jmp     short loc_18002CBEB
0x18002cbe1  mov     dword ptr [rbx+3A0h], 40007h
0x18002cbeb  mov     rcx, r13; lpCriticalSection
0x18002cbee  call    cs:__imp_LeaveCriticalSection
0x18002cbf4  mov     esi, [rbp+57h+var_C0]
0x18002cbf7  xor     r13d, r13d
0x18002cbfa  mov     r14, [rbp+57h+var_B8]
0x18002cbfe  jmp     loc_18002C945
```
