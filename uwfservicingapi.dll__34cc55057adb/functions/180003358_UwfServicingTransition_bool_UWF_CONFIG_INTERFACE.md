# UwfServicingTransition(bool,UWF_CONFIG_INTERFACE *)

- ea: `0x180003358`
- end: `0x180003483`
- name: `?UwfServicingTransition@@YAJ_NPEAUUWF_CONFIG_INTERFACE@@@Z`
- size: `299`
- prototype: `__int64 __fastcall(char, struct UWF_CONFIG_INTERFACE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180002620`

## callees

- `0x180002878`
- `0x180002a20`
- `0x180003358`
- `0x180003540`
- `0x18000370c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800033dc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800033dc`

## string_xrefs

- `0x1800033b6`: `SYSTEM\CurrentControlSet\Services\UwfServicingSvc\Servicing`
- `0x18000342c`: `Unknown Servicing state or bad data stored in registry`

## pseudocode

```c
__int64 __fastcall UwfServicingTransition(char a1, struct UWF_CONFIG_INTERFACE *a2)
{
  signed int Status; // ebx
  LSTATUS ValueW; // eax
  bool v6; // sf
  struct UWF_CONFIG_INTERFACE *v8; // rcx
  DWORD pcbData; // [rsp+40h] [rbp-18h] BYREF
  DWORD pdwType[5]; // [rsp+44h] [rbp-14h] BYREF
  int pvData; // [rsp+70h] [rbp+18h] BYREF
  unsigned int v12; // [rsp+78h] [rbp+20h] BYREF

  v12 = 0;
  pvData = 0;
  Status = UwfServicingGetStatus((enum UWFSERVICING_STATUS *)&v12);
  if ( Status < 0 )
    goto LABEL_7;
  pvData = 0;
  pdwType[0] = 0;
  pcbData = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Services\\UwfServicingSvc\\Servicing",
             L"Information",
             0x20000010u,
             pdwType,
             &pvData,
             &pcbData);
  Status = 0;
  if ( ValueW != 2 )
    Status = ValueW;
  v6 = Status < 0;
  if ( Status > 0 )
  {
    Status = (unsigned __int16)Status | 0x80070000;
    v6 = Status < 0;
  }
  if ( v6 )
  {
LABEL_7:
    UwfServicingLog(0, 1, (unsigned int)Status, L"Failed to query servicing status");
    return (unsigned int)Status;
  }
  if ( v12 )
  {
    if ( v12 != 1 )
    {
      if ( v12 != 3 )
      {
        UwfServicingLog(0, 1, v12, L"Unknown Servicing state or bad data stored in registry");
        return 2147942413LL;
      }
      v8 = a2;
      if ( !a1 )
        return anonymous_namespace_::disableServicing(v8);
      return anonymous_namespace_::enableServicing(v8);
    }
    if ( !a1 )
    {
      v8 = a2;
      return anonymous_namespace_::disableServicing(v8);
    }
    return 2147483661LL;
  }
  if ( !a1 )
    return 2147483661LL;
  v8 = a2;
  return anonymous_namespace_::enableServicing(v8);
}

```

## disassembly

```asm
0x180003358  mov     rax, rsp
0x18000335b  mov     [rax+8], rbx
0x18000335f  mov     [rax+10h], rsi
0x180003363  push    rdi
0x180003364  sub     rsp, 50h
0x180003368  mov     sil, cl
0x18000336b  mov     dword ptr [rax+20h], 0
0x180003372  lea     rcx, [rax+20h]; enum UWFSERVICING_STATUS *
0x180003376  mov     dword ptr [rax+18h], 0
0x18000337d  mov     rdi, rdx
0x180003380  call    ?UwfServicingGetStatus@@YAJPEAW4UWFSERVICING_STATUS@@@Z; UwfServicingGetStatus(UWFSERVICING_STATUS *)
0x180003385  mov     ebx, eax
0x180003387  test    eax, eax
0x180003389  js      short loc_1800033FB
0x18000338b  lea     rax, [rsp+58h+var_18]
0x180003390  mov     [rsp+58h+arg_10], 0
0x180003398  mov     [rsp+58h+pcbData], rax; pcbData
0x18000339d  lea     r8, Value; "Information"
0x1800033a4  lea     rax, [rsp+58h+arg_10]
0x1800033a9  mov     [rsp+58h+var_14], 0
0x1800033b1  mov     [rsp+58h+pvData], rax; pvData
0x1800033b6  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Uw"...
0x1800033bd  lea     rax, [rsp+58h+var_14]
0x1800033c2  mov     [rsp+58h+var_18], 4
0x1800033ca  mov     r9d, 20000010h; dwFlags
0x1800033d0  mov     [rsp+58h+pdwType], rax; pdwType
0x1800033d5  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800033dc  call    cs:__imp_RegGetValueW
0x1800033e2  xor     ebx, ebx
0x1800033e4  cmp     eax, 2
0x1800033e7  cmovnz  ebx, eax
0x1800033ea  test    ebx, ebx
0x1800033ec  jle     short loc_1800033F9
0x1800033ee  movzx   ebx, bx
0x1800033f1  or      ebx, 80070000h
0x1800033f7  test    ebx, ebx
0x1800033f9  jns     short loc_180003415
0x1800033fb  lea     r9, aFailedToQueryS; "Failed to query servicing status"
0x180003402  mov     r8d, ebx
0x180003405  mov     edx, 1
0x18000340a  xor     ecx, ecx
0x18000340c  call    ?UwfServicingLog@@YAJW4UWFSERVICING_MODULE_ID@@W4UWFSERVICING_LOG_TYPE@@KPEBGZZ; UwfServicingLog(UWFSERVICING_MODULE_ID,UWFSERVICING_LOG_TYPE,ulong,ushort const *,...)
0x180003411  mov     eax, ebx
0x180003413  jmp     short loc_180003473
0x180003415  mov     r8d, [rsp+58h+arg_18]
0x18000341a  mov     eax, r8d
0x18000341d  test    r8d, r8d
0x180003420  jz      short loc_18000345F
0x180003422  sub     eax, 1
0x180003425  jz      short loc_180003450
0x180003427  cmp     eax, 2
0x18000342a  jz      short loc_180003446
0x18000342c  lea     r9, aUnknownServici; "Unknown Servicing state or bad data sto"...
0x180003433  mov     edx, 1
0x180003438  xor     ecx, ecx
0x18000343a  call    ?UwfServicingLog@@YAJW4UWFSERVICING_MODULE_ID@@W4UWFSERVICING_LOG_TYPE@@KPEBGZZ; UwfServicingLog(UWFSERVICING_MODULE_ID,UWFSERVICING_LOG_TYPE,ulong,ushort const *,...)
0x18000343f  mov     eax, 8007000Dh
0x180003444  jmp     short loc_180003473
0x180003446  mov     rcx, rdi
0x180003449  test    sil, sil
0x18000344c  jnz     short loc_18000346E
0x18000344e  jmp     short loc_180003458
0x180003450  test    sil, sil
0x180003453  jnz     short loc_180003464
0x180003455  mov     rcx, rdi
0x180003458  call    _anonymous_namespace___disableServicing
0x18000345d  jmp     short loc_180003473
0x18000345f  test    sil, sil
0x180003462  jnz     short loc_18000346B
0x180003464  mov     eax, 8000000Dh
0x180003469  jmp     short loc_180003473
0x18000346b  mov     rcx, rdi; struct UWF_CONFIG_INTERFACE *
0x18000346e  call    _anonymous_namespace___enableServicing
0x180003473  mov     rbx, [rsp+58h+arg_0]
0x180003478  mov     rsi, [rsp+58h+arg_8]
0x18000347d  add     rsp, 50h
0x180003481  pop     rdi
0x180003482  retn
```
