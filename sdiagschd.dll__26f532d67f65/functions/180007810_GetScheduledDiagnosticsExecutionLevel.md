# GetScheduledDiagnosticsExecutionLevel

- ea: `0x180007810`
- end: `0x1800078d5`
- name: `GetScheduledDiagnosticsExecutionLevel`
- size: `197`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800081f0`

## callees

- `0x1800072cc`
- `0x1800073ec`
- `0x180007810`
- `0x18000b13c`

## string_xrefs

- `0x180007835`: `GetScheduledDiagnosticsExecutionLevel`

## pseudocode

```c
__int64 __fastcall GetScheduledDiagnosticsExecutionLevel(_DWORD *a1)
{
  unsigned int v2; // ebx
  int v3; // r8d
  int v4; // r9d
  int GroupPolicySetting; // eax
  int AdminSetting; // eax
  unsigned int v8; // [rsp+30h] [rbp+8h] BYREF

  v8 = 0;
  if ( a1 )
  {
    GroupPolicySetting = SchdpGetGroupPolicySetting(&v8);
    v2 = GroupPolicySetting;
    if ( GroupPolicySetting < 0 )
    {
      v4 = GroupPolicySetting;
      v3 = 573;
      goto LABEL_4;
    }
    switch ( v8 )
    {
      case 0u:
        AdminSetting = SchdpGetAdminSetting(&v8);
        v2 = AdminSetting;
        if ( AdminSetting >= 0 )
        {
          *a1 = 4 - (v8 != 0);
          return v2;
        }
        v4 = AdminSetting;
        v3 = 581;
        goto LABEL_4;
      case 1u:
        *a1 = 2;
        return v2;
      case 2u:
        *a1 = 1;
        return v2;
      case 3u:
        *a1 = 0;
        return v2;
    }
    v2 = -2147467259;
    v3 = 602;
  }
  else
  {
    v2 = -2147024809;
    v3 = 570;
  }
  v4 = v2;
LABEL_4:
  SdpDebugTrace(1u, L"GetScheduledDiagnosticsExecutionLevel", v3, v4);
  return v2;
}

```

## disassembly

```asm
0x180007810  mov     [rsp+arg_8], rbx
0x180007815  push    rdi
0x180007816  sub     rsp, 20h
0x18000781a  and     [rsp+28h+arg_0], 0
0x18000781f  mov     rdi, rcx
0x180007822  test    rcx, rcx
0x180007825  jnz     short loc_180007848
0x180007827  mov     ebx, 80070057h
0x18000782c  mov     r8d, 23Ah; int
0x180007832  mov     r9d, ebx; int
0x180007835  lea     rdx, aGetscheduleddi_0; "GetScheduledDiagnosticsExecutionLevel"
0x18000783c  mov     ecx, 1; Level
0x180007841  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180007846  jmp     short loc_1800078C7
0x180007848  lea     rcx, [rsp+28h+arg_0]; unsigned int *
0x18000784d  call    ?SchdpGetGroupPolicySetting@@YAJPEAK@Z; SchdpGetGroupPolicySetting(ulong *)
0x180007852  mov     ebx, eax
0x180007854  test    eax, eax
0x180007856  jns     short loc_180007863
0x180007858  mov     r9d, eax
0x18000785b  mov     r8d, 23Dh
0x180007861  jmp     short loc_180007835
0x180007863  mov     eax, [rsp+28h+arg_0]
0x180007867  test    eax, eax
0x180007869  jz      short loc_18000789C
0x18000786b  sub     eax, 1
0x18000786e  jz      short loc_180007894
0x180007870  sub     eax, 1
0x180007873  jz      short loc_18000788C
0x180007875  cmp     eax, 1
0x180007878  jz      short loc_180007887
0x18000787a  mov     ebx, 80004005h
0x18000787f  mov     r8d, 25Ah
0x180007885  jmp     short loc_180007832
0x180007887  and     dword ptr [rdi], 0
0x18000788a  jmp     short loc_1800078C7
0x18000788c  mov     dword ptr [rdi], 1
0x180007892  jmp     short loc_1800078C7
0x180007894  mov     dword ptr [rdi], 2
0x18000789a  jmp     short loc_1800078C7
0x18000789c  lea     rcx, [rsp+28h+arg_0]; unsigned int *
0x1800078a1  call    ?SchdpGetAdminSetting@@YAJPEAK@Z; SchdpGetAdminSetting(ulong *)
0x1800078a6  mov     ebx, eax
0x1800078a8  test    eax, eax
0x1800078aa  jns     short loc_1800078BA
0x1800078ac  mov     r9d, eax
0x1800078af  mov     r8d, 245h
0x1800078b5  jmp     loc_180007835
0x1800078ba  mov     eax, [rsp+28h+arg_0]
0x1800078be  neg     eax
0x1800078c0  sbb     ecx, ecx
0x1800078c2  add     ecx, 4
0x1800078c5  mov     [rdi], ecx
0x1800078c7  mov     eax, ebx
0x1800078c9  mov     rbx, [rsp+28h+arg_8]
0x1800078ce  add     rsp, 20h
0x1800078d2  pop     rdi
0x1800078d3  retn
```
