# TpmRegistry::CreateKey(ushort const *,void *)

- ea: `0x14002fc8c`
- end: `0x14002fd16`
- name: `?CreateKey@TpmRegistry@@SAJPEBGPEAX@Z`
- size: `138`
- prototype: `static int(const unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400222b8`

## callees

- `0x14000a19c`
- `0x14000e030`
- `0x14002f87c`
- `0x14002fc8c`
- `0x1400454a0`

## pseudocode

```c
__int64 __fastcall TpmRegistry::CreateKey(const unsigned __int16 *a1, void *a2)
{
  int inited; // ebx
  struct _UNICODE_STRING v6; // [rsp+20h] [rbp-18h] BYREF

  v6 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_S(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_94e382a665763f71bd92d92ac5fb5bd5_Traceguids, a1);
  inited = TpmRegistry::InitRegistryKey(&v6, a1, 0x23u);
  if ( inited >= 0 )
    inited = TpmRegistry::CreateKey(&v6, a2);
  TpmFree(v6.Buffer);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x14002fc8c  mov     [rsp+arg_0], rbx
0x14002fc91  push    rdi
0x14002fc92  sub     rsp, 30h
0x14002fc96  xorps   xmm0, xmm0
0x14002fc99  mov     rdi, rdx
0x14002fc9c  movups  xmmword ptr [rsp+38h+var_18.Length], xmm0
0x14002fca1  mov     rbx, rcx
0x14002fca4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002fcab  lea     rax, WPP_GLOBAL_Control
0x14002fcb2  cmp     rcx, rax
0x14002fcb5  jz      short loc_14002FCD6
0x14002fcb7  mov     eax, [rcx+2Ch]
0x14002fcba  test    al, 4
0x14002fcbc  jz      short loc_14002FCD6
0x14002fcbe  mov     rcx, [rcx+18h]
0x14002fcc2  lea     r8, WPP_94e382a665763f71bd92d92ac5fb5bd5_Traceguids
0x14002fcc9  mov     edx, 0Eh
0x14002fcce  mov     r9, rbx
0x14002fcd1  call    WPP_SF_S
0x14002fcd6  mov     r8d, 23h ; '#'
0x14002fcdc  lea     rcx, [rsp+38h+var_18]
0x14002fce1  mov     rdx, rbx
0x14002fce4  call    ?InitRegistryKey@TpmRegistry@@CAJPEAU_UNICODE_STRING@@PEBGW4KEY_VALUES@1@@Z; TpmRegistry::InitRegistryKey(_UNICODE_STRING *,ushort const *,TpmRegistry::KEY_VALUES)
0x14002fce9  mov     ebx, eax
0x14002fceb  test    eax, eax
0x14002fced  js      short loc_14002FCFE
0x14002fcef  mov     rdx, rdi; void *
0x14002fcf2  lea     rcx, [rsp+38h+var_18]; struct _UNICODE_STRING *
0x14002fcf7  call    ?CreateKey@TpmRegistry@@CAJPEAU_UNICODE_STRING@@PEAX@Z; TpmRegistry::CreateKey(_UNICODE_STRING *,void *)
0x14002fcfc  mov     ebx, eax
0x14002fcfe  mov     rcx, [rsp+38h+var_18.Buffer]; void *
0x14002fd03  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x14002fd08  mov     eax, ebx
0x14002fd0a  mov     rbx, [rsp+38h+arg_0]
0x14002fd0f  add     rsp, 30h
0x14002fd13  pop     rdi
0x14002fd14  retn
```
