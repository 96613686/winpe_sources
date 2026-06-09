# CWinSATTaskMangerTask::FinalConstruct(void)

- ea: `0x180020784`
- end: `0x180020829`
- name: `?FinalConstruct@CWinSATTaskMangerTask@@QEAAJXZ`
- size: `165`
- prototype: `__int64 __fastcall(CWinSATTaskMangerTask *this, __int64, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180017c90`
- `0x180018490`

## callees

- `0x1800173a4`
- `0x1800173d0`
- `0x18001c414`
- `0x180020784`
- `0x180031010`

## string_xrefs

- `0x1800207f7`: `Cannot create registry key %s`
- `0x180020806`: `base\winsat\api-dll\winsattaskmangertask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CWinSATTaskMangerTask::FinalConstruct(
        CWinSATTaskMangerTask *this,
        __int64 a2,
        __int64 a3,
        unsigned __int16 *a4)
{
  void (__fastcall *v5)(__int64 *, __int64, _QWORD); // rax
  unsigned int v7; // [rsp+20h] [rbp-48h]
  HKEY v8[5]; // [rsp+40h] [rbp-28h] BYREF

  if ( !*((_BYTE *)this + 184) )
  {
    v5 = (void (__fastcall *)(__int64 *, __int64, _QWORD))*((_QWORD *)this + 18);
    if ( v5 )
      v5(qword_1800487B0, 142082, 0);
    *((_BYTE *)this + 184) = 1;
  }
  memset(v8, 0, 24);
  if ( (unsigned int)ATL::CRegKey::Create(
                       v8,
                       HKEY_LOCAL_MACHINE,
                       L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WinSATAPI",
                       a4,
                       v7) )
    Record_Win32Error_w(
      "base\\winsat\\api-dll\\winsattaskmangertask.cpp",
      (char)L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WinSATAPI");
  ATL::CRegKey::Close(v8);
  return 0;
}

```

## disassembly

```asm
0x180020784  push    rbx
0x180020786  sub     rsp, 60h
0x18002078a  cmp     byte ptr [rcx+0B8h], 0
0x180020791  mov     rbx, rcx
0x180020794  jnz     short loc_1800207BD
0x180020796  mov     rax, [rcx+90h]
0x18002079d  test    rax, rax
0x1800207a0  jz      short loc_1800207B6
0x1800207a2  xor     r8d, r8d
0x1800207a5  lea     rcx, qword_1800487B0
0x1800207ac  mov     edx, 22B02h
0x1800207b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207b6  mov     byte ptr [rbx+0B8h], 1
0x1800207bd  lea     rbx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800207c4  mov     [rsp+68h+var_28], 0
0x1800207cd  mov     r8, rbx; lpSubKey
0x1800207d0  mov     [rsp+68h+var_20], 0
0x1800207d9  mov     rdx, 0FFFFFFFF80000002h; hKey
0x1800207e0  mov     [rsp+68h+var_18], 0
0x1800207e9  lea     rcx, [rsp+68h+var_28]; this
0x1800207ee  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x1800207f3  test    eax, eax
0x1800207f5  jz      short loc_180020817
0x1800207f7  lea     r9, aCannotCreateRe; "Cannot create registry key %s"
0x1800207fe  mov     qword ptr [rsp+68h+var_48], rbx; char
0x180020803  mov     r8d, eax
0x180020806  lea     rcx, aBaseWinsatApiD_1; "base\\winsat\\api-dll\\winsattaskmanger"...
0x18002080d  mov     edx, 44h ; 'D'
0x180020812  call    Record_Win32Error_w
0x180020817  lea     rcx, [rsp+68h+var_28]; this
0x18002081c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180020821  xor     eax, eax
0x180020823  add     rsp, 60h
0x180020827  pop     rbx
0x180020828  retn
```
