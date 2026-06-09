# EcDeleteSubscription

- ea: `0x180004640`
- end: `0x180004779`
- name: `EcDeleteSubscription`
- size: `313`
- prototype: `BOOL __stdcall(LPCWSTR SubscriptionName, DWORD Flags)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001aac`
- `0x1800025d0`
- `0x1800027ac`
- `0x180004640`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000467a`
- `RPCRT4!NdrClientCall3` at `0x18000467a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004690`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004690`

## pseudocode

```c
BOOL __stdcall EcDeleteSubscription(LPCWSTR SubscriptionName, DWORD Flags)
{
  BOOL v2; // edi
  DWORD Pointer; // ebx
  wmi::Exception *v5; // [rsp+30h] [rbp-88h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+38h] [rbp-80h] BYREF
  _BYTE v7[72]; // [rsp+70h] [rbp-48h] BYREF

  try
  {
    v2 = 0;
    if ( Flags )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_ad46ba0b25a435688d5858c8a9a9bb6f_Traceguids, 87);
      }
      wmi::GenericException::GenericException(
        (wmi::GenericException *)pExceptionObject,
        0x57u,
        "admin\\wmi\\events\\forwarding\\collector\\api\\evcoll.cpp",
        360);
      throw (wmi::GenericException *)pExceptionObject;
    }
    if ( !SubscriptionName )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_ad46ba0b25a435688d5858c8a9a9bb6f_Traceguids, 87);
      }
      wmi::GenericException::GenericException(
        (wmi::GenericException *)v7,
        0x57u,
        "admin\\wmi\\events\\forwarding\\collector\\api\\evcoll.cpp",
        362);
      throw (wmi::GenericException *)v7;
    }
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              3u,
                              0,
                              g_bindingHandle,
                              SubscriptionName,
                              0).Pointer;
  }
  catch ( wmi::Exception *v5 )
  {
    v2 = 0;
    Pointer = (**(__int64 (__fastcall ***)(wmi::Exception *))v5)(v5);
  }
  SetLastError(Pointer);
  LOBYTE(v2) = Pointer == 0;
  return v2;
}

```

## disassembly

```asm
0x180004640  mov     [rsp+arg_0], rbx
0x180004645  push    rdi
0x180004646  sub     rsp, 0B0h
0x18000464d  xor     edi, edi
0x18000464f  test    edx, edx
0x180004651  jnz     short loc_1800046AF
0x180004653  test    rcx, rcx
0x180004656  jz      loc_180004712
0x18000465c  mov     [rsp+0B8h+var_90], edi
0x180004660  mov     [rsp+0B8h+var_98], rcx
0x180004665  mov     r9, cs:?g_bindingHandle@@3PEAXEA; void * g_bindingHandle
0x18000466c  xor     r8d, r8d; pReturnValue
0x18000466f  lea     edx, [r8+3]; nProcNum
0x180004673  lea     rcx, pProxyInfo; pProxyInfo
0x18000467a  call    cs:__imp_NdrClientCall3
0x180004680  mov     rbx, rax
0x180004683  jmp     short loc_18000468E
0x180004685  xor     edi, edi
0x180004687  mov     ebx, [rsp+0B8h+arg_8]
0x18000468e  mov     ecx, ebx; dwErrCode
0x180004690  call    cs:__imp_SetLastError
0x180004696  test    ebx, ebx
0x180004698  setz    dil
0x18000469c  mov     eax, edi
0x18000469e  mov     rbx, [rsp+0B8h+arg_0]
0x1800046a6  add     rsp, 0B0h
0x1800046ad  pop     rdi
0x1800046ae  retn
0x1800046af  lea     rax, WPP_GLOBAL_Control
0x1800046b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800046bd  cmp     rcx, rax
0x1800046c0  jz      short loc_1800046E5
0x1800046c2  test    byte ptr [rcx+1Ch], 1
0x1800046c6  jz      short loc_1800046E5
0x1800046c8  cmp     byte ptr [rcx+19h], 2
0x1800046cc  jb      short loc_1800046E5
0x1800046ce  lea     edx, [rdi+1Ah]
0x1800046d1  lea     r9d, [rdi+57h]
0x1800046d5  lea     r8, WPP_ad46ba0b25a435688d5858c8a9a9bb6f_Traceguids
0x1800046dc  mov     rcx, [rcx+10h]
0x1800046e0  call    WPP_SF_D
0x1800046e5  mov     r9d, 168h; int
0x1800046eb  lea     r8, aAdminWmiEvents_1; "admin\\wmi\\events\\forwarding\\collect"...
0x1800046f2  mov     edx, 57h ; 'W'; unsigned int
0x1800046f7  lea     rcx, [rsp+0B8h+pExceptionObject]; this
0x1800046fc  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x180004701  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180004708  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x18000470d  call    _CxxThrowException_0
0x180004712  lea     rax, WPP_GLOBAL_Control
0x180004719  mov     rcx, cs:WPP_GLOBAL_Control
0x180004720  cmp     rcx, rax
0x180004723  jz      short loc_18000474A
0x180004725  test    byte ptr [rcx+1Ch], 1
0x180004729  jz      short loc_18000474A
0x18000472b  cmp     byte ptr [rcx+19h], 2
0x18000472f  jb      short loc_18000474A
0x180004731  mov     edx, 1Bh
0x180004736  lea     r9d, [rdx+3Ch]
0x18000473a  lea     r8, WPP_ad46ba0b25a435688d5858c8a9a9bb6f_Traceguids
0x180004741  mov     rcx, [rcx+10h]
0x180004745  call    WPP_SF_D
0x18000474a  mov     r9d, 16Ah; int
0x180004750  lea     r8, aAdminWmiEvents_1; "admin\\wmi\\events\\forwarding\\collect"...
0x180004757  mov     edx, 57h ; 'W'; unsigned int
0x18000475c  lea     rcx, [rsp+0B8h+var_48]; this
0x180004761  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x180004766  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000476d  lea     rcx, [rsp+0B8h+var_48]; pExceptionObject
0x180004772  call    _CxxThrowException_0
```
