# EcIsConfigRequired(int *)

- ea: `0x180003870`
- end: `0x180003922`
- name: `?EcIsConfigRequired@@YAHPEAH@Z`
- size: `178`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x180001aac`
- `0x1800025d0`
- `0x1800027ac`
- `0x180003870`
- `0x18000908c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000389e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000389e`

## pseudocode

```c
__int64 __fastcall EcIsConfigRequired(int *a1)
{
  unsigned int v1; // ebx
  DWORD v2; // edi
  wmi::Exception *v4; // [rsp+20h] [rbp-48h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+28h] [rbp-40h] BYREF

  try
  {
    v1 = 0;
    v2 = 0;
    if ( !a1 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_ad46ba0b25a435688d5858c8a9a9bb6f_Traceguids, 87);
      }
      wmi::GenericException::GenericException(
        (wmi::GenericException *)pExceptionObject,
        0x57u,
        "admin\\wmi\\events\\forwarding\\collector\\api\\evcoll.cpp",
        689);
      throw (wmi::GenericException *)pExceptionObject;
    }
    *a1 = SetupChannelAndService(0);
  }
  catch ( wmi::Exception *v4 )
  {
    v1 = 0;
    v2 = (**(__int64 (__fastcall ***)(wmi::Exception *))v4)(v4);
  }
  SetLastError(v2);
  LOBYTE(v1) = v2 == 0;
  return v1;
}

```

## disassembly

```asm
0x180003870  mov     [rsp+arg_8], rbx
0x180003875  mov     [rsp+arg_10], rsi
0x18000387a  push    rdi
0x18000387b  sub     rsp, 60h
0x18000387f  mov     rsi, rcx
0x180003882  xor     ebx, ebx
0x180003884  mov     edi, ebx
0x180003886  test    rcx, rcx
0x180003889  jz      short loc_1800038BD
0x18000388b  xor     ecx, ecx; int
0x18000388d  call    ?SetupChannelAndService@@YAHH@Z; SetupChannelAndService(int)
0x180003892  mov     [rsi], eax
0x180003894  jmp     short loc_18000389C
0x180003896  xor     ebx, ebx
0x180003898  mov     edi, [rsp+68h+arg_0]
0x18000389c  mov     ecx, edi; dwErrCode
0x18000389e  call    cs:__imp_SetLastError
0x1800038a4  test    edi, edi
0x1800038a6  setz    bl
0x1800038a9  mov     eax, ebx
0x1800038ab  lea     r11, [rsp+68h+var_8]
0x1800038b0  mov     rbx, [r11+18h]
0x1800038b4  mov     rsi, [r11+20h]
0x1800038b8  mov     rsp, r11
0x1800038bb  pop     rdi
0x1800038bc  retn
0x1800038bd  lea     rax, WPP_GLOBAL_Control
0x1800038c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038cb  cmp     rcx, rax
0x1800038ce  jz      short loc_1800038F3
0x1800038d0  test    byte ptr [rcx+1Ch], 1
0x1800038d4  jz      short loc_1800038F3
0x1800038d6  cmp     byte ptr [rcx+19h], 2
0x1800038da  jb      short loc_1800038F3
0x1800038dc  lea     edx, [rsi+29h]
0x1800038df  lea     r9d, [rsi+57h]
0x1800038e3  lea     r8, WPP_ad46ba0b25a435688d5858c8a9a9bb6f_Traceguids
0x1800038ea  mov     rcx, [rcx+10h]
0x1800038ee  call    WPP_SF_D
0x1800038f3  mov     r9d, 2B1h; int
0x1800038f9  lea     r8, aAdminWmiEvents_1; "admin\\wmi\\events\\forwarding\\collect"...
0x180003900  mov     edx, 57h ; 'W'; unsigned int
0x180003905  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18000390a  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x18000390f  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180003916  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000391b  call    _CxxThrowException_0
```
