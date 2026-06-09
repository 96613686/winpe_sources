# SdbpGetMergeSdbsDisabled

- ea: `0x140017498`
- end: `0x140017593`
- name: `SdbpGetMergeSdbsDisabled`
- size: `251`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14001687c`

## callees

- `0x14001008c`
- `0x140010568`
- `0x140010a68`
- `0x140017498`
- `0x14001759c`

## import_xrefs

- `ntdll!ZwClose` at `0x14001757b`
- `ntdll!ZwClose` at `0x14001757b`

## string_xrefs

- `0x1400174d3`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates`
- `0x1400174f6`: `AslRegistryGetKey failed to open SdbUpdates key [%x]`

## pseudocode

```c
__int64 __fastcall SdbpGetMergeSdbsDisabled(_DWORD *a1)
{
  unsigned int v2; // ebx
  int Key; // eax
  char *v4; // rdi
  int UInt32; // eax
  int v7; // [rsp+48h] [rbp+10h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp+18h] BYREF

  v7 = 0;
  Handle = 0;
  if ( (unsigned int)SdbpGetMergeSdbsSupported() )
  {
    Key = AslRegistryGetKey(
            &Handle,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates",
            0x80000100);
    v4 = (char *)Handle;
    v2 = Key;
    if ( Key >= 0 )
    {
      UInt32 = AslRegistryGetUInt32((__int64)&v7, (__int64)Handle, L"DisableDoubleQuerySdbs");
      v2 = UInt32;
      if ( UInt32 == -1073741772 )
      {
        v2 = 0;
        *a1 = 0;
      }
      else if ( UInt32 >= 0 )
      {
        v2 = 0;
        *a1 = v7 != 0;
      }
      else
      {
        AslLogCallPrintf(1, "SdbpGetMergeSdbsDisabled", 1128, "Failed to query reg value.");
      }
    }
    else if ( Key != -1073741772 )
    {
      AslLogCallPrintf(1, "SdbpGetMergeSdbsDisabled", 1116, "AslRegistryGetKey failed to open SdbUpdates key [%x]", Key);
    }
    if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      ZwClose(v4);
  }
  else
  {
    return (unsigned int)-1073741772;
  }
  return v2;
}

```

## disassembly

```asm
0x140017498  mov     rax, rsp
0x14001749b  mov     [rax+8], rbx
0x14001749f  mov     [rax+20h], rsi
0x1400174a3  push    rdi
0x1400174a4  sub     rsp, 30h
0x1400174a8  mov     rsi, rcx
0x1400174ab  mov     dword ptr [rax+10h], 0
0x1400174b2  mov     qword ptr [rax+18h], 0
0x1400174ba  call    SdbpGetMergeSdbsSupported
0x1400174bf  test    eax, eax
0x1400174c1  jnz     short loc_1400174CD
0x1400174c3  mov     ebx, 0C0000034h
0x1400174c8  jmp     loc_140017581
0x1400174cd  mov     r8d, 80000100h
0x1400174d3  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows NT\\Curren"...
0x1400174da  lea     rcx, [rsp+38h+Handle]
0x1400174df  call    AslRegistryGetKey
0x1400174e4  mov     rdi, [rsp+38h+Handle]
0x1400174e9  mov     ebx, eax
0x1400174eb  test    eax, eax
0x1400174ed  jns     short loc_14001751A
0x1400174ef  cmp     eax, 0C0000034h
0x1400174f4  jz      short loc_14001756E
0x1400174f6  lea     r9, aAslregistryget_3; "AslRegistryGetKey failed to open SdbUpd"...
0x1400174fd  mov     [rsp+38h+var_18], eax
0x140017501  mov     r8d, 45Ch
0x140017507  lea     rdx, aSdbpgetmergesd_1; "SdbpGetMergeSdbsDisabled"
0x14001750e  mov     ecx, 1
0x140017513  call    AslLogCallPrintf
0x140017518  jmp     short loc_14001756E
0x14001751a  lea     r8, aDisabledoubleq; "DisableDoubleQuerySdbs"
0x140017521  mov     rdx, rdi
0x140017524  lea     rcx, [rsp+38h+arg_8]
0x140017529  call    AslRegistryGetUInt32
0x14001752e  mov     ebx, eax
0x140017530  cmp     eax, 0C0000034h
0x140017535  jnz     short loc_14001753D
0x140017537  xor     ebx, ebx
0x140017539  mov     [rsi], ebx
0x14001753b  jmp     short loc_14001756E
0x14001753d  test    eax, eax
0x14001753f  jns     short loc_140017561
0x140017541  lea     r9, aFailedToQueryR_0; "Failed to query reg value."
0x140017548  mov     r8d, 468h
0x14001754e  lea     rdx, aSdbpgetmergesd_1; "SdbpGetMergeSdbsDisabled"
0x140017555  mov     ecx, 1
0x14001755a  call    AslLogCallPrintf
0x14001755f  jmp     short loc_14001756E
0x140017561  xor     eax, eax
0x140017563  cmp     [rsp+38h+arg_8], eax
0x140017567  setnz   al
0x14001756a  xor     ebx, ebx
0x14001756c  mov     [rsi], eax
0x14001756e  lea     rax, [rdi-1]
0x140017572  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140017576  ja      short loc_140017581
0x140017578  mov     rcx, rdi; Handle
0x14001757b  call    cs:__imp_ZwClose
0x140017581  mov     rsi, [rsp+38h+arg_18]
0x140017586  mov     eax, ebx
0x140017588  mov     rbx, [rsp+38h+arg_0]
0x14001758d  add     rsp, 30h
0x140017591  pop     rdi
0x140017592  retn
```
