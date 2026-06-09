# CWinSATTaskMangerTask::SQMLogWinSATRun(ulong,unsigned __int64)

- ea: `0x180021904`
- end: `0x180021a95`
- name: `?SQMLogWinSATRun@CWinSATTaskMangerTask@@AEAAXK_K@Z`
- size: `401`
- prototype: `void __fastcall(CWinSATTaskMangerTask *__hidden this, unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180020428`

## callees

- `0x18000e6ac`
- `0x18001c21c`
- `0x18001c414`
- `0x1800214fc`
- `0x180021904`
- `0x18002bd2c`
- `0x18002be4c`
- `0x180031010`

## string_xrefs

- `0x180021958`: `base\winsat\api-dll\winsattaskmangertaskregistry.cpp`
- `0x180021949`: `cannot read the task error count from the registry`
- `0x180021a25`: `Cannot write %s to the registry`
- `0x18002199a`: `base\winsat\api-dll\winsattaskmangertasksqm.cpp`
- `0x1800219b5`: `base\winsat\api-dll\winsattaskmangertasksqm.cpp`
- `0x180021a34`: `base\winsat\api-dll\winsattaskmangertasksqm.cpp`

## pseudocode

```c
void __fastcall CWinSATTaskMangerTask::SQMLogWinSATRun(CWinSATTaskMangerTask *this, int a2, unsigned __int64 a3)
{
  unsigned __int64 v5; // rcx
  unsigned int v6; // ebx
  unsigned __int64 v7; // rdi
  void (__fastcall *v8)(__int64 *, __int64, _QWORD); // rax
  void (__fastcall *v9)(__int64 *, __int64, __int64); // rax
  char v10; // [rsp+20h] [rbp-18h]
  bool v11; // [rsp+48h] [rbp+10h] BYREF
  unsigned __int64 v12; // [rsp+58h] [rbp+20h] BYREF

  if ( a2 == 1 )
  {
    v12 = 0;
    v11 = 0;
    if ( (unsigned int)RegHelper::ReadQWORDValue(0, L"WindeployTimeDate", &v12) )
    {
      Record_Win32Error_w("base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp", v10);
      v6 = 65532;
    }
    else
    {
      v5 = v12;
      if ( v11 )
        v5 = 0;
      if ( v5 )
      {
        if ( v5 < a3 )
        {
          v7 = a3 - v5;
          if ( v7 < 0xFFFF )
          {
            v6 = v7;
            Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertasksqm.cpp", 86, "Seconds Since WinDeploy = %u", v7);
          }
          else
          {
            v6 = 65534;
            Record_InternalError_w("base\\winsat\\api-dll\\winsattaskmangertasksqm.cpp");
          }
        }
        else
        {
          Record_InternalError_w("base\\winsat\\api-dll\\winsattaskmangertasksqm.cpp");
          v6 = 0xFFFF;
        }
      }
      else
      {
        v6 = 65533;
      }
    }
    v8 = (void (__fastcall *)(__int64 *, __int64, _QWORD))*((_QWORD *)this + 17);
    if ( v8 )
      v8(qword_1800487B0, 6435, v6);
    if ( (unsigned int)RegHelper::WriteDWORDValue(v5, L"WinDeployToFirstRunDuration", v6) )
      Record_Win32Error_w("base\\winsat\\api-dll\\winsattaskmangertasksqm.cpp", (char)L"WinDeployToFirstRunDuration");
  }
  v11 = 0;
  if ( CWinSATTaskMangerTask::HasIdleWinSATCompletedOnce(this, &v11) && !v11 )
  {
    v9 = (void (__fastcall *)(__int64 *, __int64, __int64))*((_QWORD *)this + 20);
    if ( v9 )
      v9(qword_1800487B0, 6437, 1);
  }
}

```

## disassembly

```asm
0x180021904  mov     rax, rsp
0x180021907  mov     [rax+8], rbx
0x18002190b  mov     [rax+18h], rsi
0x18002190f  push    rdi
0x180021910  sub     rsp, 30h
0x180021914  mov     rdi, r8
0x180021917  mov     rsi, rcx
0x18002191a  cmp     edx, 1
0x18002191d  jnz     loc_180021A45
0x180021923  lea     r9, [rax+10h]
0x180021927  mov     qword ptr [rax+20h], 0
0x18002192f  lea     r8, [rax+20h]
0x180021933  mov     byte ptr [rax+10h], 0
0x180021937  lea     rdx, aWindeploytimed; "WindeployTimeDate"
0x18002193e  xor     ecx, ecx
0x180021940  call    ?ReadQWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBGAEA_KPEA_N@Z; RegHelper::ReadQWORDValue(WinSATRegistryKeys::Enum,ushort const *,unsigned __int64 &,bool *)
0x180021945  test    eax, eax
0x180021947  jz      short loc_18002196E
0x180021949  lea     r9, aCannotReadTheT; "cannot read the task error count from t"...
0x180021950  mov     r8d, eax
0x180021953  mov     edx, 0C4h
0x180021958  lea     rcx, aBaseWinsatApiD_3; "base\\winsat\\api-dll\\winsattaskmanger"...
0x18002195f  call    Record_Win32Error_w
0x180021964  mov     ebx, 0FFFCh
0x180021969  jmp     loc_1800219EF
0x18002196e  mov     rcx, [rsp+38h+arg_18]
0x180021973  xor     eax, eax
0x180021975  cmp     [rsp+38h+arg_8], al
0x180021979  cmovnz  rcx, rax
0x18002197d  test    rcx, rcx
0x180021980  jnz     short loc_180021989
0x180021982  mov     ebx, 0FFFDh
0x180021987  jmp     short loc_1800219EF
0x180021989  cmp     rcx, rdi
0x18002198c  jb      short loc_1800219AD
0x18002198e  lea     r8, aWindeployTimeI; "Windeploy time is greater than the time"...
0x180021995  mov     edx, 40h ; '@'
0x18002199a  lea     rcx, aBaseWinsatApiD_2; "base\\winsat\\api-dll\\winsattaskmanger"...
0x1800219a1  call    Record_InternalError_w
0x1800219a6  mov     ebx, 0FFFFh
0x1800219ab  jmp     short loc_1800219EF
0x1800219ad  sub     rdi, rcx
0x1800219b0  mov     ebx, 0FFFFh
0x1800219b5  lea     rcx, aBaseWinsatApiD_2; "base\\winsat\\api-dll\\winsattaskmanger"...
0x1800219bc  cmp     rdi, rbx
0x1800219bf  jb      short loc_1800219D9
0x1800219c1  lea     r8, aWindeployTimeD; "Windeploy time difference is greater th"...
0x1800219c8  mov     edx, 4Eh ; 'N'
0x1800219cd  mov     ebx, 0FFFEh
0x1800219d2  call    Record_InternalError_w
0x1800219d7  jmp     short loc_1800219EF
0x1800219d9  mov     r9d, edi
0x1800219dc  lea     r8, aSecondsSinceWi; "Seconds Since WinDeploy = %u"
0x1800219e3  mov     edx, 56h ; 'V'
0x1800219e8  mov     ebx, edi
0x1800219ea  call    Log_Text_F
0x1800219ef  mov     rax, [rsi+88h]
0x1800219f6  test    rax, rax
0x1800219f9  jz      short loc_180021A0F
0x1800219fb  mov     r8d, ebx
0x1800219fe  lea     rcx, qword_1800487B0
0x180021a05  mov     edx, 1923h
0x180021a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a0f  mov     r8d, ebx
0x180021a12  lea     rbx, aWindeploytofir; "WinDeployToFirstRunDuration"
0x180021a19  mov     rdx, rbx
0x180021a1c  call    ?WriteDWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBGK@Z; RegHelper::WriteDWORDValue(WinSATRegistryKeys::Enum,ushort const *,ulong)
0x180021a21  test    eax, eax
0x180021a23  jz      short loc_180021A45
0x180021a25  lea     r9, aCannotWriteSTo; "Cannot write %s to the registry"
0x180021a2c  mov     qword ptr [rsp+38h+var_18], rbx; char
0x180021a31  mov     r8d, eax
0x180021a34  lea     rcx, aBaseWinsatApiD_2; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180021a3b  mov     edx, 66h ; 'f'
0x180021a40  call    Record_Win32Error_w
0x180021a45  lea     rdx, [rsp+38h+arg_8]; bool *
0x180021a4a  mov     [rsp+38h+arg_8], 0
0x180021a4f  mov     rcx, rsi; this
0x180021a52  call    ?HasIdleWinSATCompletedOnce@CWinSATTaskMangerTask@@AEAA_NAEA_N@Z; CWinSATTaskMangerTask::HasIdleWinSATCompletedOnce(bool &)
0x180021a57  test    al, al
0x180021a59  jz      short loc_180021A85
0x180021a5b  cmp     [rsp+38h+arg_8], 0
0x180021a60  jnz     short loc_180021A85
0x180021a62  mov     rax, [rsi+0A0h]
0x180021a69  test    rax, rax
0x180021a6c  jz      short loc_180021A85
0x180021a6e  mov     edx, 1925h
0x180021a73  lea     rcx, qword_1800487B0
0x180021a7a  mov     r8d, 1
0x180021a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a85  mov     rbx, [rsp+38h+arg_0]
0x180021a8a  mov     rsi, [rsp+38h+arg_10]
0x180021a8f  add     rsp, 30h
0x180021a93  pop     rdi
0x180021a94  retn
```
