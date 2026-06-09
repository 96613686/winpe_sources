# TpmRegistry::DeleteKey(ushort const *,int)

- ea: `0x14003005c`
- end: `0x1400300d9`
- name: `?DeleteKey@TpmRegistry@@SAJPEBGH@Z`
- size: `125`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400222b8`
- `0x140022570`

## callees

- `0x14000a19c`
- `0x14002fe48`
- `0x14003005c`
- `0x1400303bc`
- `0x1400454a0`

## pseudocode

```c
__int64 __fastcall TpmRegistry::DeleteKey(const unsigned __int16 *a1, int a2, int a3)
{
  int inited; // ebx
  struct _UNICODE_STRING v6; // [rsp+30h] [rbp-18h] BYREF

  v6 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_Ss(WPP_GLOBAL_Control->AttachedDevice, a2, a3, (_DWORD)a1, (__int64)"false");
  inited = TpmRegistry::InitRegistryKey(&v6, a1, 0x23u);
  if ( inited >= 0 )
    inited = TpmRegistry::DeleteKey(&v6, 0);
  TpmFree(v6.Buffer);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x14003005c  push    rbx
0x14003005e  sub     rsp, 40h
0x140030062  xorps   xmm0, xmm0
0x140030065  mov     rbx, rcx
0x140030068  movups  xmmword ptr [rsp+48h+var_18.Length], xmm0
0x14003006d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140030074  lea     rax, WPP_GLOBAL_Control
0x14003007b  cmp     rcx, rax
0x14003007e  jz      short loc_14003009F
0x140030080  mov     eax, [rcx+2Ch]
0x140030083  test    al, 4
0x140030085  jz      short loc_14003009F
0x140030087  mov     rcx, [rcx+18h]
0x14003008b  lea     rax, aFalse; "false"
0x140030092  mov     r9, rbx
0x140030095  mov     [rsp+48h+var_28], rax
0x14003009a  call    WPP_SF_Ss
0x14003009f  mov     r8d, 23h ; '#'
0x1400300a5  lea     rcx, [rsp+48h+var_18]
0x1400300aa  mov     rdx, rbx
0x1400300ad  call    ?InitRegistryKey@TpmRegistry@@CAJPEAU_UNICODE_STRING@@PEBGW4KEY_VALUES@1@@Z; TpmRegistry::InitRegistryKey(_UNICODE_STRING *,ushort const *,TpmRegistry::KEY_VALUES)
0x1400300b2  mov     ebx, eax
0x1400300b4  test    eax, eax
0x1400300b6  js      short loc_1400300C6
0x1400300b8  xor     edx, edx; int
0x1400300ba  lea     rcx, [rsp+48h+var_18]; struct _UNICODE_STRING *
0x1400300bf  call    ?DeleteKey@TpmRegistry@@CAJPEAU_UNICODE_STRING@@H@Z; TpmRegistry::DeleteKey(_UNICODE_STRING *,int)
0x1400300c4  mov     ebx, eax
0x1400300c6  mov     rcx, [rsp+48h+var_18.Buffer]; void *
0x1400300cb  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x1400300d0  mov     eax, ebx
0x1400300d2  add     rsp, 40h
0x1400300d6  pop     rbx
0x1400300d7  retn
```
