# IsUsbRedirectionEnabled

- ea: `0x14001271c`
- end: `0x1400128b0`
- name: `IsUsbRedirectionEnabled`
- size: `404`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14001303c`

## callees

- `0x14000aa30`
- `0x14001271c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14001275d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400127bc`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001280f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001275d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400127bc`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001280f`

## string_xrefs

- `0x1400127ac`: `\REGISTRY\MACHINE\Software\Policies\Microsoft\Windows NT\Terminal Services\Client`
- `0x14001273e`: `\REGISTRY\MACHINE\Software`

## pseudocode

```c
__int64 IsUsbRedirectionEnabled()
{
  unsigned int v0; // ebx
  int v1; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-30h] BYREF
  struct _UNICODE_STRING v4; // [rsp+50h] [rbp-20h] BYREF
  struct _UNICODE_STRING v5; // [rsp+60h] [rbp-10h] BYREF
  int v6; // [rsp+80h] [rbp+10h] BYREF
  __int64 v7; // [rsp+88h] [rbp+18h] BYREF
  __int64 v8; // [rsp+90h] [rbp+20h] BYREF

  v6 = 0;
  v7 = 0;
  v8 = 0;
  DestinationString = 0;
  v4 = 0;
  v5 = 0;
  RtlInitUnicodeString(&DestinationString, L"\\REGISTRY\\MACHINE\\Software");
  if ( ((int (__fastcall *)(struct _LIST_ENTRY *, _QWORD, struct _UNICODE_STRING *, __int64, _QWORD, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[114].Blink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         0,
         &DestinationString,
         131097,
         0,
         &v8) >= 0 )
  {
    v0 = 2;
    RtlInitUnicodeString(
      &v4,
      L"\\REGISTRY\\MACHINE\\Software\\Policies\\Microsoft\\Windows NT\\Terminal Services\\Client");
    if ( ((int (__fastcall *)(struct _LIST_ENTRY *, _QWORD, struct _UNICODE_STRING *, __int64, _QWORD, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[114].Blink)(
           WPP_MAIN_CB.Queue.ListEntry.Blink,
           0,
           &v4,
           131097,
           0,
           &v7) >= 0 )
    {
      RtlInitUnicodeString(&v5, L"fUsbRedirectionEnableMode");
      if ( ((int (__fastcall *)(struct _LIST_ENTRY *, __int64, struct _UNICODE_STRING *, int *))WPP_MAIN_CB.Queue.ListEntry.Flink[120].Flink)(
             WPP_MAIN_CB.Queue.ListEntry.Blink,
             v7,
             &v5,
             &v6) >= 0 )
      {
        v1 = v6;
      }
      else
      {
        v1 = 0;
        v6 = 0;
      }
      if ( v1 )
        v0 = 1;
    }
  }
  else
  {
    v0 = 0;
  }
  if ( v8 )
    ((void (__fastcall *)(struct _LIST_ENTRY *))WPP_MAIN_CB.Queue.ListEntry.Flink[115].Blink)(WPP_MAIN_CB.Queue.ListEntry.Blink);
  if ( v7 )
    ((void (__fastcall *)(struct _LIST_ENTRY *))WPP_MAIN_CB.Queue.ListEntry.Flink[115].Blink)(WPP_MAIN_CB.Queue.ListEntry.Blink);
  return v0;
}

```

## disassembly

```asm
0x14001271c  mov     [rsp-8+arg_18], rbx
0x140012721  push    rbp
0x140012722  mov     rbp, rsp
0x140012725  sub     rsp, 70h
0x140012729  xorps   xmm0, xmm0
0x14001272c  mov     [rbp+arg_0], 0
0x140012733  xorps   xmm1, xmm1
0x140012736  mov     [rbp+arg_8], 0
0x14001273e  lea     rdx, SourceString; "\\REGISTRY\\MACHINE\\Software"
0x140012745  mov     [rbp+arg_10], 0
0x14001274d  lea     rcx, [rbp+DestinationString]; DestinationString
0x140012751  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140012755  movups  xmmword ptr [rbp+var_20.Length], xmm1
0x140012759  movups  xmmword ptr [rbp+var_10.Length], xmm0
0x14001275d  call    cs:__imp_RtlInitUnicodeString
0x140012764  nop     dword ptr [rax+rax+00h]
0x140012769  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140012770  lea     rcx, [rbp+arg_10]
0x140012774  mov     [rsp+70h+var_48], rcx
0x140012779  lea     r8, [rbp+DestinationString]
0x14001277d  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140012784  mov     r9d, 20019h
0x14001278a  xor     edx, edx
0x14001278c  mov     [rsp+70h+var_50], 0
0x140012795  mov     rax, [rax+728h]
0x14001279c  call    _guard_dispatch_icall
0x1400127a1  test    eax, eax
0x1400127a3  jns     short loc_1400127AC
0x1400127a5  xor     ebx, ebx
0x1400127a7  jmp     loc_140012859
0x1400127ac  lea     rdx, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\Software\\Policies"...
0x1400127b3  mov     ebx, 2
0x1400127b8  lea     rcx, [rbp+var_20]; DestinationString
0x1400127bc  call    cs:__imp_RtlInitUnicodeString
0x1400127c3  nop     dword ptr [rax+rax+00h]
0x1400127c8  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400127cf  lea     rcx, [rbp+arg_8]
0x1400127d3  mov     [rsp+70h+var_48], rcx
0x1400127d8  lea     r8, [rbp+var_20]
0x1400127dc  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400127e3  mov     r9d, 20019h
0x1400127e9  xor     edx, edx
0x1400127eb  mov     [rsp+70h+var_50], 0
0x1400127f4  mov     rax, [rax+728h]
0x1400127fb  call    _guard_dispatch_icall
0x140012800  test    eax, eax
0x140012802  js      short loc_140012859
0x140012804  lea     rdx, aFusbredirectio; "fUsbRedirectionEnableMode"
0x14001280b  lea     rcx, [rbp+var_10]; DestinationString
0x14001280f  call    cs:__imp_RtlInitUnicodeString
0x140012816  nop     dword ptr [rax+rax+00h]
0x14001281b  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140012822  lea     r9, [rbp+arg_0]
0x140012826  mov     rdx, [rbp+arg_8]
0x14001282a  lea     r8, [rbp+var_10]
0x14001282e  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140012835  mov     rax, [rax+780h]
0x14001283c  call    _guard_dispatch_icall
0x140012841  test    eax, eax
0x140012843  jns     short loc_14001284C
0x140012845  xor     eax, eax
0x140012847  mov     [rbp+arg_0], eax
0x14001284a  jmp     short loc_14001284F
0x14001284c  mov     eax, [rbp+arg_0]
0x14001284f  test    eax, eax
0x140012851  mov     ecx, 1
0x140012856  cmovnz  ebx, ecx
0x140012859  mov     rdx, [rbp+arg_10]
0x14001285d  test    rdx, rdx
0x140012860  jz      short loc_14001287C
0x140012862  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140012869  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140012870  mov     rax, [rax+738h]
0x140012877  call    _guard_dispatch_icall
0x14001287c  mov     rdx, [rbp+arg_8]
0x140012880  test    rdx, rdx
0x140012883  jz      short loc_14001289F
0x140012885  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x14001288c  mov     rax, [rcx+738h]
0x140012893  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14001289a  call    _guard_dispatch_icall
0x14001289f  mov     eax, ebx
0x1400128a1  mov     rbx, [rsp+70h+arg_18]
0x1400128a9  add     rsp, 70h
0x1400128ad  pop     rbp
0x1400128ae  retn
```
