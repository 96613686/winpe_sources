# TpmRegistry::OpenKey(TpmRegistry::KEY_VALUES,ulong,void * *)

- ea: `0x140005a88`
- end: `0x140005ade`
- name: `?OpenKey@TpmRegistry@@CAJW4KEY_VALUES@1@KPEAPEAX@Z`
- size: `86`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400055dc`
- `0x1400059fc`
- `0x14001a2e0`

## callees

- `0x140005a88`
- `0x14000a0a4`
- `0x140039780`

## pseudocode

```c
__int64 __fastcall TpmRegistry::OpenKey(unsigned int a1, unsigned int a2, _QWORD *a3)
{
  int v4; // ebx
  __int64 v6; // [rsp+48h] [rbp+20h] BYREF

  v6 = 0;
  v4 = TpmRegistry::OpenKey(a1, a2, &v6);
  if ( v4 >= 0 )
    *a3 = (*((__int64 (__fastcall **)(PKDPC, __int64))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 232))(
            WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
            v6);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140005a88  mov     [rsp+arg_0], rbx
0x140005a8d  push    rdi
0x140005a8e  sub     rsp, 20h
0x140005a92  mov     rdi, r8
0x140005a95  mov     [rsp+28h+arg_18], 0
0x140005a9e  lea     r8, [rsp+28h+arg_18]
0x140005aa3  call    ?OpenKey@TpmRegistry@@CAJW4KEY_VALUES@1@KPEAPEAUWDFKEY__@@@Z; TpmRegistry::OpenKey(TpmRegistry::KEY_VALUES,ulong,WDFKEY__ * *)
0x140005aa8  mov     ebx, eax
0x140005aaa  test    eax, eax
0x140005aac  js      short loc_140005AD0
0x140005aae  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140005ab5  mov     rdx, [rsp+28h+arg_18]
0x140005aba  mov     rax, [rcx+740h]
0x140005ac1  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140005ac8  call    _guard_dispatch_icall
0x140005acd  mov     [rdi], rax
0x140005ad0  mov     eax, ebx
0x140005ad2  mov     rbx, [rsp+28h+arg_0]
0x140005ad7  add     rsp, 20h
0x140005adb  pop     rdi
0x140005adc  retn
```
