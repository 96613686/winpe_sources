# CUserSetting::GetBlackboard(void)

- ea: `0x1800051e0`
- end: `0x18000525a`
- name: `?GetBlackboard@CUserSetting@@IEAAPEAU_BLACKBOARD@@XZ`
- size: `122`
- prototype: `struct _BLACKBOARD *__fastcall(CUserSetting *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180004eb0`
- `0x180005570`
- `0x180005f20`
- `0x180005f90`
- `0x180006570`

## callees

- `0x180004df0`
- `0x1800051e0`
- `0x1800054d0`
- `0x18000892c`

## import_xrefs

- `WDSCORE!CurrentIP` at `0x180005218`
- `WDSCORE!CurrentIP` at `0x180005218`
- `WDSCORE!WdsCreateBlackboard` at `0x180005203`
- `WDSCORE!WdsCreateBlackboard` at `0x180005203`

## pseudocode

```c
struct _BLACKBOARD *__fastcall CUserSetting::GetBlackboard(CUserSetting *this)
{
  __int64 Blackboard; // rax
  void *v3; // rax
  unsigned int v4; // ecx
  const unsigned __int16 *v5; // r9

  CUserSetting::AcquireMutex(this);
  if ( !*((_QWORD *)this + 2) )
  {
    Blackboard = WdsCreateBlackboard(8, L"SetupInfo", 0);
    *((_QWORD *)this + 2) = Blackboard;
    if ( !Blackboard )
    {
      v3 = (void *)CurrentIP();
      Ui_Assert(v4, "_pBlackboard != 0", 0x77u, v5, L"CUserSetting::GetBlackboard", v3);
    }
  }
  CUserSetting::ReleaseMutex(this);
  return (struct _BLACKBOARD *)*((_QWORD *)this + 2);
}

```

## disassembly

```asm
0x1800051e0  push    rbx
0x1800051e2  sub     rsp, 30h
0x1800051e6  mov     rbx, rcx
0x1800051e9  call    ?AcquireMutex@CUserSetting@@IEAAXXZ; CUserSetting::AcquireMutex(void)
0x1800051ee  cmp     qword ptr [rbx+10h], 0
0x1800051f3  jnz     short loc_180005247
0x1800051f5  xor     r8d, r8d
0x1800051f8  lea     rdx, aSetupinfo; "SetupInfo"
0x1800051ff  lea     ecx, [r8+8]
0x180005203  call    cs:__imp_WdsCreateBlackboard
0x18000520a  nop     dword ptr [rax+rax+00h]
0x18000520f  mov     [rbx+10h], rax
0x180005213  test    rax, rax
0x180005216  jnz     short loc_180005247
0x180005218  call    cs:__imp_CurrentIP
0x18000521f  nop     dword ptr [rax+rax+00h]
0x180005224  mov     [rsp+38h+var_10], rax; void *
0x180005229  mov     r8d, 77h ; 'w'; unsigned int
0x18000522f  lea     rdx, aPblackboard0; "_pBlackboard != 0"
0x180005236  lea     rax, aCusersettingGe; "CUserSetting::GetBlackboard"
0x18000523d  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x180005242  call    ?Ui_Assert@@YAXKPEBDKPEBG1PEAX@Z; Ui_Assert(ulong,char const *,ulong,ushort const *,ushort const *,void *)
0x180005247  mov     rcx, rbx; this
0x18000524a  call    ?ReleaseMutex@CUserSetting@@IEAAXXZ; CUserSetting::ReleaseMutex(void)
0x18000524f  mov     rax, [rbx+10h]
0x180005253  add     rsp, 30h
0x180005257  pop     rbx
0x180005258  retn
```
