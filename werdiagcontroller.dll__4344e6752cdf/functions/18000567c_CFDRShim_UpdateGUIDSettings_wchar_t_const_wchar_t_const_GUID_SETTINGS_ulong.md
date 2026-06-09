# CFDRShim::UpdateGUIDSettings(wchar_t const *,wchar_t const *,GUID_SETTINGS *,ulong *)

- ea: `0x18000567c`
- end: `0x18000576b`
- name: `?UpdateGUIDSettings@CFDRShim@@AEAAJPEB_W0PEAUGUID_SETTINGS@@PEAK@Z`
- size: `239`
- prototype: `__int64 __fastcall(CFDRShim *this, const wchar_t *, const wchar_t *, GUID *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180004e1c`

## callees

- `0x18000567c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800056c1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800056fb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000571d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000573f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800056c1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800056fb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000571d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000573f`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180005708`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18000572a`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18000574c`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180005708`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18000572a`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18000574c`
- `ntdll!RtlInitUnicodeString` at `0x1800056db`
- `ntdll!RtlInitUnicodeString` at `0x1800056db`
- `ntdll!DbgPrintEx` at `0x1800056a7`
- `ntdll!DbgPrintEx` at `0x1800056a7`
- `ntdll!RtlGUIDFromString` at `0x1800056e9`
- `ntdll!RtlGUIDFromString` at `0x1800056e9`

## pseudocode

```c
__int64 __fastcall CFDRShim::UpdateGUIDSettings(
        CFDRShim *this,
        const wchar_t *a2,
        const wchar_t *a3,
        GUID *a4,
        unsigned int *a5)
{
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  if ( a4 )
  {
    if ( (unsigned int)_o__wcsicmp(a2, L"Guid") )
    {
      if ( (unsigned int)_o__wcsicmp(a2, L"Level") )
      {
        if ( (unsigned int)_o__wcsicmp(a2, L"Flags") )
        {
          if ( !(unsigned int)_o__wcsicmp(a2, L"CircularSize") )
            *a5 = _o__wtoi(a3);
        }
        else
        {
          *(_DWORD *)&a4[1].Data2 = _o__wtoi(a3);
        }
      }
      else
      {
        a4[1].Data1 = _o__wtoi(a3);
      }
    }
    else
    {
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, a3);
      RtlGUIDFromString(&DestinationString, a4);
    }
    return 0;
  }
  else
  {
    DbgPrintEx(0x96u, 0, "WERDIAG: Invalid arguments: pointer to settings structure cannot be null\n");
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18000567c  mov     [rsp+arg_0], rbx
0x180005681  mov     [rsp+arg_8], rsi
0x180005686  push    rdi
0x180005687  sub     rsp, 30h
0x18000568b  mov     rdi, r9
0x18000568e  mov     rbx, r8
0x180005691  mov     rsi, rdx
0x180005694  test    r9, r9
0x180005697  jnz     short loc_1800056B7
0x180005699  lea     r8, aWerdiagInvalid_5; "WERDIAG: Invalid arguments: pointer to "...
0x1800056a0  xor     edx, edx; Level
0x1800056a2  mov     ecx, 96h; ComponentId
0x1800056a7  call    cs:__imp_DbgPrintEx
0x1800056ad  mov     eax, 80070057h
0x1800056b2  jmp     loc_18000575B
0x1800056b7  lea     rdx, aGuid; "Guid"
0x1800056be  mov     rcx, rsi
0x1800056c1  call    cs:__imp__o__wcsicmp
0x1800056c7  test    eax, eax
0x1800056c9  jnz     short loc_1800056F1
0x1800056cb  xorps   xmm0, xmm0
0x1800056ce  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x1800056d3  mov     rdx, rbx; SourceString
0x1800056d6  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x1800056db  call    cs:__imp_RtlInitUnicodeString
0x1800056e1  mov     rdx, rdi; Guid
0x1800056e4  lea     rcx, [rsp+38h+DestinationString]; GuidString
0x1800056e9  call    cs:__imp_RtlGUIDFromString
0x1800056ef  jmp     short loc_180005759
0x1800056f1  lea     rdx, aLevel; "Level"
0x1800056f8  mov     rcx, rsi
0x1800056fb  call    cs:__imp__o__wcsicmp
0x180005701  test    eax, eax
0x180005703  jnz     short loc_180005713
0x180005705  mov     rcx, rbx
0x180005708  call    cs:__imp__o__wtoi
0x18000570e  mov     [rdi+10h], eax
0x180005711  jmp     short loc_180005759
0x180005713  lea     rdx, aFlags; "Flags"
0x18000571a  mov     rcx, rsi
0x18000571d  call    cs:__imp__o__wcsicmp
0x180005723  test    eax, eax
0x180005725  jnz     short loc_180005735
0x180005727  mov     rcx, rbx
0x18000572a  call    cs:__imp__o__wtoi
0x180005730  mov     [rdi+14h], eax
0x180005733  jmp     short loc_180005759
0x180005735  lea     rdx, aCircularsize; "CircularSize"
0x18000573c  mov     rcx, rsi
0x18000573f  call    cs:__imp__o__wcsicmp
0x180005745  test    eax, eax
0x180005747  jnz     short loc_180005759
0x180005749  mov     rcx, rbx
0x18000574c  call    cs:__imp__o__wtoi
0x180005752  mov     rcx, [rsp+38h+arg_20]
0x180005757  mov     [rcx], eax
0x180005759  xor     eax, eax
0x18000575b  mov     rbx, [rsp+38h+arg_0]
0x180005760  mov     rsi, [rsp+38h+arg_8]
0x180005765  add     rsp, 30h
0x180005769  pop     rdi
0x18000576a  retn
```
