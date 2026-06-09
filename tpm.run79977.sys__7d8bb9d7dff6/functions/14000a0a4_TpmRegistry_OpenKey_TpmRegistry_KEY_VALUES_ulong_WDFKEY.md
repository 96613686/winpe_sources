# TpmRegistry::OpenKey(TpmRegistry::KEY_VALUES,ulong,WDFKEY__ * *)

- ea: `0x14000a0a4`
- end: `0x14000a15e`
- name: `?OpenKey@TpmRegistry@@CAJW4KEY_VALUES@1@KPEAPEAUWDFKEY__@@@Z`
- size: `186`
- prototype: ``
- caller_count: `9`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140005840`
- `0x140005a88`
- `0x140009db0`
- `0x140009fc8`
- `0x14000a4f0`
- `0x14000b0a8`
- `0x14000b6c8`
- `0x14000b7a8`
- `0x14000bf68`

## callees

- `0x140009278`
- `0x14000a0a4`
- `0x14000a164`
- `0x140039780`
- `0x1400454a0`

## pseudocode

```c
__int64 __fastcall TpmRegistry::OpenKey(unsigned int a1, unsigned int a2, _QWORD *a3)
{
  int inited; // ebx
  void *v8[2]; // [rsp+40h] [rbp-18h] BYREF

  *a3 = 0;
  *(_OWORD *)v8 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_94e382a665763f71bd92d92ac5fb5bd5_Traceguids, a1);
  inited = TpmRegistry::InitRegistryKey(v8, a1);
  if ( inited >= 0 )
    inited = (*((__int64 (__fastcall **)(PKDPC, _QWORD, void **, _QWORD, _QWORD, _QWORD *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp
              + 229))(
               WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
               0,
               v8,
               a2,
               0,
               a3);
  TpmFree(v8[1]);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x14000a0a4  mov     [rsp+arg_0], rbx
0x14000a0a9  mov     [rsp+arg_8], rsi
0x14000a0ae  push    rdi
0x14000a0af  sub     rsp, 50h
0x14000a0b3  xorps   xmm0, xmm0
0x14000a0b6  mov     qword ptr [r8], 0
0x14000a0bd  movups  xmmword ptr [rsp+58h+var_18], xmm0
0x14000a0c2  mov     rdi, r8
0x14000a0c5  mov     esi, edx
0x14000a0c7  mov     ebx, ecx
0x14000a0c9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000a0d0  lea     rax, WPP_GLOBAL_Control
0x14000a0d7  cmp     rcx, rax
0x14000a0da  jz      short loc_14000A0FB
0x14000a0dc  mov     eax, [rcx+2Ch]
0x14000a0df  test    al, 4
0x14000a0e1  jz      short loc_14000A0FB
0x14000a0e3  mov     rcx, [rcx+18h]
0x14000a0e7  lea     r8, WPP_94e382a665763f71bd92d92ac5fb5bd5_Traceguids
0x14000a0ee  mov     edx, 0Dh
0x14000a0f3  mov     r9d, ebx
0x14000a0f6  call    WPP_SF_d
0x14000a0fb  mov     edx, ebx
0x14000a0fd  lea     rcx, [rsp+58h+var_18]
0x14000a102  call    ?InitRegistryKey@TpmRegistry@@CAJPEAU_UNICODE_STRING@@W4KEY_VALUES@1@@Z; TpmRegistry::InitRegistryKey(_UNICODE_STRING *,TpmRegistry::KEY_VALUES)
0x14000a107  mov     ebx, eax
0x14000a109  test    eax, eax
0x14000a10b  js      short loc_14000A141
0x14000a10d  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14000a114  lea     r8, [rsp+58h+var_18]
0x14000a119  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14000a120  mov     r9d, esi
0x14000a123  mov     [rsp+58h+var_30], rdi
0x14000a128  xor     edx, edx
0x14000a12a  mov     [rsp+58h+var_38], 0
0x14000a133  mov     rax, [rax+728h]
0x14000a13a  call    _guard_dispatch_icall
0x14000a13f  mov     ebx, eax
0x14000a141  mov     rcx, [rsp+58h+var_18+8]; void *
0x14000a146  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x14000a14b  mov     rsi, [rsp+58h+arg_8]
0x14000a150  mov     eax, ebx
0x14000a152  mov     rbx, [rsp+58h+arg_0]
0x14000a157  add     rsp, 50h
0x14000a15b  pop     rdi
0x14000a15c  retn
```
