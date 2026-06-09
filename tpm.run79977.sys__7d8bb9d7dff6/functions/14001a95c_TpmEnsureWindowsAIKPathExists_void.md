# TpmEnsureWindowsAIKPathExists(void)

- ea: `0x14001a95c`
- end: `0x14001a9ce`
- name: `?TpmEnsureWindowsAIKPathExists@@YAJXZ`
- size: `114`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140005370`

## callees

- `0x14001647c`
- `0x14001a95c`

## string_xrefs

- `0x14001a963`: `TpmDriverMsDataPath`
- `0x14001a96a`: `\Device\BootDevice\ProgramData\Microsoft`
- `0x14001a97d`: `TpmDriverMsCryptoPath`
- `0x14001a984`: `\Device\BootDevice\ProgramData\Microsoft\Crypto`
- `0x14001a997`: `TpmDriverMsPcpKspPath`
- `0x14001a99e`: `\Device\BootDevice\ProgramData\Microsoft\Crypto\PCPKSP`
- `0x14001a9b5`: `TpmDriverMsWinAikPath`
- `0x14001a9bc`: `\Device\BootDevice\ProgramData\Microsoft\Crypto\PCPKSP\WindowsAIK`

## pseudocode

```c
__int64 TpmEnsureWindowsAIKPathExists(void)
{
  __int64 result; // rax

  result = TpmEnsureWindowsAIKDirExists(L"\\Device\\BootDevice\\ProgramData\\Microsoft", L"TpmDriverMsDataPath", 0);
  if ( (int)result >= 0 )
  {
    result = TpmEnsureWindowsAIKDirExists(
               L"\\Device\\BootDevice\\ProgramData\\Microsoft\\Crypto",
               L"TpmDriverMsCryptoPath",
               0);
    if ( (int)result >= 0 )
    {
      result = TpmEnsureWindowsAIKDirExists(
                 L"\\Device\\BootDevice\\ProgramData\\Microsoft\\Crypto\\PCPKSP",
                 L"TpmDriverMsPcpKspPath",
                 0);
      if ( (int)result >= 0 )
        return TpmEnsureWindowsAIKDirExists(
                 L"\\Device\\BootDevice\\ProgramData\\Microsoft\\Crypto\\PCPKSP\\WindowsAIK",
                 L"TpmDriverMsWinAikPath",
                 qword_14003D090);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001a95c  sub     rsp, 28h
0x14001a960  xor     r8d, r8d; void *
0x14001a963  lea     rdx, aTpmdrivermsdat; "TpmDriverMsDataPath"
0x14001a96a  lea     rcx, aDeviceBootdevi_2; "\\Device\\BootDevice\\ProgramData\\Micr"...
0x14001a971  call    ?TpmEnsureWindowsAIKDirExists@@YAJPEBG0PEAX@Z; TpmEnsureWindowsAIKDirExists(ushort const *,ushort const *,void *)
0x14001a976  test    eax, eax
0x14001a978  js      short loc_14001A9C8
0x14001a97a  xor     r8d, r8d; void *
0x14001a97d  lea     rdx, aTpmdrivermscry; "TpmDriverMsCryptoPath"
0x14001a984  lea     rcx, aDeviceBootdevi; "\\Device\\BootDevice\\ProgramData\\Micr"...
0x14001a98b  call    ?TpmEnsureWindowsAIKDirExists@@YAJPEBG0PEAX@Z; TpmEnsureWindowsAIKDirExists(ushort const *,ushort const *,void *)
0x14001a990  test    eax, eax
0x14001a992  js      short loc_14001A9C8
0x14001a994  xor     r8d, r8d; void *
0x14001a997  lea     rdx, aTpmdrivermspcp; "TpmDriverMsPcpKspPath"
0x14001a99e  lea     rcx, aDeviceBootdevi_0; "\\Device\\BootDevice\\ProgramData\\Micr"...
0x14001a9a5  call    ?TpmEnsureWindowsAIKDirExists@@YAJPEBG0PEAX@Z; TpmEnsureWindowsAIKDirExists(ushort const *,ushort const *,void *)
0x14001a9aa  test    eax, eax
0x14001a9ac  js      short loc_14001A9C8
0x14001a9ae  lea     r8, qword_14003D090; void *
0x14001a9b5  lea     rdx, aTpmdrivermswin; "TpmDriverMsWinAikPath"
0x14001a9bc  lea     rcx, aDeviceBootdevi_1; "\\Device\\BootDevice\\ProgramData\\Micr"...
0x14001a9c3  call    ?TpmEnsureWindowsAIKDirExists@@YAJPEBG0PEAX@Z; TpmEnsureWindowsAIKDirExists(ushort const *,ushort const *,void *)
0x14001a9c8  add     rsp, 28h
0x14001a9cc  retn
```
