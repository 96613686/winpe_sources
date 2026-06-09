# TpmRegistry::CreateKey(TpmRegistry::KEY_VALUES,void *)

- ea: `0x14002fd1c`
- end: `0x14002fd9e`
- name: `?CreateKey@TpmRegistry@@SAJW4KEY_VALUES@1@PEAX@Z`
- size: `130`
- prototype: `static int __high(enum TpmRegistry::KEY_VALUES, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400222b8`
- `0x14002fda4`

## callees

- `0x140009278`
- `0x14000a164`
- `0x14002f87c`
- `0x14002fd1c`
- `0x1400454a0`

## pseudocode

```c
__int64 __fastcall TpmRegistry::CreateKey(unsigned int a1, void *a2)
{
  int inited; // ebx
  struct _UNICODE_STRING v6; // [rsp+20h] [rbp-18h] BYREF

  v6 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_94e382a665763f71bd92d92ac5fb5bd5_Traceguids, a1);
  inited = TpmRegistry::InitRegistryKey(&v6, a1);
  if ( inited >= 0 )
    inited = TpmRegistry::CreateKey(&v6, a2);
  TpmFree(v6.Buffer);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x14002fd1c  mov     [rsp+arg_0], rbx
0x14002fd21  push    rdi
0x14002fd22  sub     rsp, 30h
0x14002fd26  xorps   xmm0, xmm0
0x14002fd29  mov     rdi, rdx
0x14002fd2c  movups  xmmword ptr [rsp+38h+var_18.Length], xmm0
0x14002fd31  mov     ebx, ecx
0x14002fd33  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002fd3a  lea     rax, WPP_GLOBAL_Control
0x14002fd41  cmp     rcx, rax
0x14002fd44  jz      short loc_14002FD65
0x14002fd46  mov     eax, [rcx+2Ch]
0x14002fd49  test    al, 4
0x14002fd4b  jz      short loc_14002FD65
0x14002fd4d  mov     rcx, [rcx+18h]
0x14002fd51  lea     r8, WPP_94e382a665763f71bd92d92ac5fb5bd5_Traceguids
0x14002fd58  mov     edx, 0Fh
0x14002fd5d  mov     r9d, ebx
0x14002fd60  call    WPP_SF_d
0x14002fd65  mov     edx, ebx
0x14002fd67  lea     rcx, [rsp+38h+var_18]
0x14002fd6c  call    ?InitRegistryKey@TpmRegistry@@CAJPEAU_UNICODE_STRING@@W4KEY_VALUES@1@@Z; TpmRegistry::InitRegistryKey(_UNICODE_STRING *,TpmRegistry::KEY_VALUES)
0x14002fd71  mov     ebx, eax
0x14002fd73  test    eax, eax
0x14002fd75  js      short loc_14002FD86
0x14002fd77  mov     rdx, rdi; void *
0x14002fd7a  lea     rcx, [rsp+38h+var_18]; struct _UNICODE_STRING *
0x14002fd7f  call    ?CreateKey@TpmRegistry@@CAJPEAU_UNICODE_STRING@@PEAX@Z; TpmRegistry::CreateKey(_UNICODE_STRING *,void *)
0x14002fd84  mov     ebx, eax
0x14002fd86  mov     rcx, [rsp+38h+var_18.Buffer]; void *
0x14002fd8b  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x14002fd90  mov     eax, ebx
0x14002fd92  mov     rbx, [rsp+38h+arg_0]
0x14002fd97  add     rsp, 30h
0x14002fd9b  pop     rdi
0x14002fd9c  retn
```
