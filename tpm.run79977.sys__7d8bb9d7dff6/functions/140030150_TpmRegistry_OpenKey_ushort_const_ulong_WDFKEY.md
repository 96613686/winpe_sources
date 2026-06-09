# TpmRegistry::OpenKey(ushort const *,ulong,WDFKEY__ * *)

- ea: `0x140030150`
- end: `0x140030212`
- name: `?OpenKey@TpmRegistry@@CAJPEBGKPEAPEAUWDFKEY__@@@Z`
- size: `194`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, struct WDFKEY__ **)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14002f7a4`
- `0x1400300e0`
- `0x140030218`

## callees

- `0x14000a19c`
- `0x14000e030`
- `0x140030150`
- `0x140039780`
- `0x1400454a0`

## pseudocode

```c
__int64 __fastcall TpmRegistry::OpenKey(const unsigned __int16 *a1, unsigned int a2, struct WDFKEY__ **a3)
{
  int inited; // ebx
  void *v8[2]; // [rsp+40h] [rbp-18h] BYREF

  *a3 = 0;
  *(_OWORD *)v8 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_S(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_94e382a665763f71bd92d92ac5fb5bd5_Traceguids, a1);
  inited = TpmRegistry::InitRegistryKey((struct _UNICODE_STRING *)v8, a1, 0x23u);
  if ( inited >= 0 )
    inited = (*((__int64 (__fastcall **)(PKDPC, _QWORD, void **, _QWORD, _QWORD, struct WDFKEY__ **))WPP_MAIN_CB.Queue.Wcb.CurrentIrp
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
0x140030150  mov     [rsp+arg_0], rbx
0x140030155  mov     [rsp+arg_8], rsi
0x14003015a  push    rdi
0x14003015b  sub     rsp, 50h
0x14003015f  xorps   xmm0, xmm0
0x140030162  mov     qword ptr [r8], 0
0x140030169  movups  xmmword ptr [rsp+58h+var_18], xmm0
0x14003016e  mov     rdi, r8
0x140030171  mov     esi, edx
0x140030173  mov     rbx, rcx
0x140030176  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003017d  lea     rax, WPP_GLOBAL_Control
0x140030184  cmp     rcx, rax
0x140030187  jz      short loc_1400301A8
0x140030189  mov     eax, [rcx+2Ch]
0x14003018c  test    al, 4
0x14003018e  jz      short loc_1400301A8
0x140030190  mov     rcx, [rcx+18h]
0x140030194  lea     r8, WPP_94e382a665763f71bd92d92ac5fb5bd5_Traceguids
0x14003019b  mov     edx, 0Ch
0x1400301a0  mov     r9, rbx
0x1400301a3  call    WPP_SF_S
0x1400301a8  mov     r8d, 23h ; '#'
0x1400301ae  lea     rcx, [rsp+58h+var_18]
0x1400301b3  mov     rdx, rbx
0x1400301b6  call    ?InitRegistryKey@TpmRegistry@@CAJPEAU_UNICODE_STRING@@PEBGW4KEY_VALUES@1@@Z; TpmRegistry::InitRegistryKey(_UNICODE_STRING *,ushort const *,TpmRegistry::KEY_VALUES)
0x1400301bb  mov     ebx, eax
0x1400301bd  test    eax, eax
0x1400301bf  js      short loc_1400301F5
0x1400301c1  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x1400301c8  lea     r8, [rsp+58h+var_18]
0x1400301cd  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x1400301d4  mov     r9d, esi
0x1400301d7  mov     [rsp+58h+var_30], rdi
0x1400301dc  xor     edx, edx
0x1400301de  mov     [rsp+58h+var_38], 0
0x1400301e7  mov     rax, [rax+728h]
0x1400301ee  call    _guard_dispatch_icall
0x1400301f3  mov     ebx, eax
0x1400301f5  mov     rcx, [rsp+58h+var_18+8]; void *
0x1400301fa  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x1400301ff  mov     rsi, [rsp+58h+arg_8]
0x140030204  mov     eax, ebx
0x140030206  mov     rbx, [rsp+58h+arg_0]
0x14003020b  add     rsp, 50h
0x14003020f  pop     rdi
0x140030210  retn
```
