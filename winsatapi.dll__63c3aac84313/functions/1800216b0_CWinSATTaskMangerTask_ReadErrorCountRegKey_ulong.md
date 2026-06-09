# CWinSATTaskMangerTask::ReadErrorCountRegKey(ulong &)

- ea: `0x1800216b0`
- end: `0x180021773`
- name: `?ReadErrorCountRegKey@CWinSATTaskMangerTask@@AEAA_NAEAK@Z`
- size: `195`
- prototype: `bool(CWinSATTaskMangerTask *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180020dcc`

## callees

- `0x18000e234`
- `0x1800173a4`
- `0x18001c414`
- `0x180021660`
- `0x1800216b0`

## string_xrefs

- `0x1800216f4`: `cannot open the winast API registry key`
- `0x180021703`: `base\winsat\api-dll\winsattaskmangertaskregistry.cpp`
- `0x180021763`: `base\winsat\api-dll\winsattaskmangertaskregistry.cpp`
- `0x180021754`: `cannot read the task error count from the registry`
- `0x180021720`: `TaskErrorCount`

## pseudocode

```c
char __fastcall CWinSATTaskMangerTask::ReadErrorCountRegKey(CWinSATTaskMangerTask *this, unsigned int *a2)
{
  int DWORDValue; // eax
  char v5; // bl
  HKEY v6[5]; // [rsp+20h] [rbp-28h] BYREF

  memset(v6, 0, 24);
  if ( (unsigned int)ATL::CRegKey::Open(
                       v6,
                       HKEY_LOCAL_MACHINE,
                       L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WinSATAPI",
                       0xF003Fu) )
  {
    Record_Win32Error_w("base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp", (char)v6[0]);
    ATL::CRegKey::Close(v6);
    return 0;
  }
  DWORDValue = ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v6, L"TaskErrorCount", a2);
  if ( DWORDValue )
  {
    if ( DWORDValue != 2 )
    {
      Record_Win32Error_w("base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp", (char)v6[0]);
      v5 = 0;
      goto LABEL_7;
    }
    *a2 = 0;
  }
  v5 = 1;
LABEL_7:
  ATL::CRegKey::Close(v6);
  return v5;
}

```

## disassembly

```asm
0x1800216b0  mov     rax, rsp
0x1800216b3  push    rbx
0x1800216b4  sub     rsp, 40h
0x1800216b8  mov     rbx, rdx
0x1800216bb  mov     qword ptr [rax-28h], 0
0x1800216c3  mov     rdx, 0FFFFFFFF80000002h; hKey
0x1800216ca  mov     qword ptr [rax-20h], 0
0x1800216d2  mov     r9d, 0F003Fh; unsigned int
0x1800216d8  mov     qword ptr [rax-18h], 0
0x1800216e0  lea     r8, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800216e7  lea     rcx, [rax-28h]; this
0x1800216eb  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800216f0  test    eax, eax
0x1800216f2  jz      short loc_18002171D
0x1800216f4  lea     r9, aCannotOpenTheW; "cannot open the winast API registry key"
0x1800216fb  mov     r8d, eax
0x1800216fe  mov     edx, 4Ah ; 'J'
0x180021703  lea     rcx, aBaseWinsatApiD_3; "base\\winsat\\api-dll\\winsattaskmanger"...
0x18002170a  call    Record_Win32Error_w
0x18002170f  lea     rcx, [rsp+48h+var_28]; this
0x180021714  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180021719  xor     al, al
0x18002171b  jmp     short loc_18002174E
0x18002171d  mov     r8, rbx; unsigned int *
0x180021720  lea     rdx, aTaskerrorcount; "TaskErrorCount"
0x180021727  lea     rcx, [rsp+48h+var_28]; this
0x18002172c  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x180021731  test    eax, eax
0x180021733  jz      short loc_180021740
0x180021735  cmp     eax, 2
0x180021738  jnz     short loc_180021754
0x18002173a  mov     dword ptr [rbx], 0
0x180021740  mov     bl, 1
0x180021742  lea     rcx, [rsp+48h+var_28]; this
0x180021747  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002174c  mov     al, bl
0x18002174e  add     rsp, 40h
0x180021752  pop     rbx
0x180021753  retn
0x180021754  lea     r9, aCannotReadTheT; "cannot read the task error count from t"...
0x18002175b  mov     r8d, eax
0x18002175e  mov     edx, 52h ; 'R'
0x180021763  lea     rcx, aBaseWinsatApiD_3; "base\\winsat\\api-dll\\winsattaskmanger"...
0x18002176a  call    Record_Win32Error_w
0x18002176f  xor     ebx, ebx
0x180021771  jmp     short loc_180021742
```
