# ReadUSBFnFeaturesFromCurrentConfiguration

- ea: `0x140043ebc`
- end: `0x14004404d`
- name: `ReadUSBFnFeaturesFromCurrentConfiguration`
- size: `401`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x140044054`

## callees

- `0x1400024b8`
- `0x140043784`
- `0x140043ebc`
- `0x1400443d4`
- `0x140044554`
- `0x140044698`
- `0x140044720`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004401b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004401b`
- `ntoskrnl!ZwClose` at `0x140043fef`
- `ntoskrnl!ZwClose` at `0x140044031`
- `ntoskrnl!ZwClose` at `0x140043fef`
- `ntoskrnl!ZwClose` at `0x140044031`

## string_xrefs

- `0x140043ee6`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\USBFN\Default`
- `0x140043ed4`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\USBFN`
- `0x140043f76`: `CurrentConfiguration`

## pseudocode

```c
__int64 __fastcall ReadUSBFnFeaturesFromCurrentConfiguration(__int64 a1, char a2)
{
  const WCHAR *v3; // rsi
  NTSTATUS v5; // eax
  int v6; // edx
  unsigned int v7; // ebx
  int v8; // r9d
  int String; // eax
  int v10; // edx
  int v11; // r8d
  int v12; // r9d
  PVOID v13; // rdi
  HANDLE Handle; // [rsp+70h] [rbp+18h] BYREF
  PVOID P; // [rsp+78h] [rbp+20h]

  Handle = 0;
  P = 0;
  v3 = L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\USBFN\\Default";
  if ( !a2 )
    v3 = L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\USBFN";
  v5 = MyRegOpenKeyForRead(a1, v3, &Handle);
  v7 = v5;
  if ( v5 >= 0 )
  {
    String = MyRegQueryString(Handle);
    v13 = P;
    v7 = String;
    if ( String >= 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_SS(WPP_GLOBAL_Control->DeviceExtension, v10, v11, v12);
      ZwClose(Handle);
      Handle = 0;
      v7 = CheckUSBFnConfiguration(a1, v13);
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 3;
      WPP_RECORDER_SF_Sd(WPP_GLOBAL_Control->DeviceExtension, v10, v11, 31);
    }
    if ( v13 )
      ExFreePoolWithTag(v13, 0);
  }
  else
  {
    if ( a2 == 1 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_18;
      v8 = 29;
      goto LABEL_7;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v8 = 30;
LABEL_7:
      LOBYTE(v6) = 4;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        1,
        v8,
        (__int64)WPP_5169c4c8089132207a438b4341aed5b6_Traceguids,
        v5);
    }
  }
LABEL_18:
  if ( Handle )
    ZwClose(Handle);
  return v7;
}

```

## disassembly

```asm
0x140043ebc  mov     r11, rsp
0x140043ebf  mov     [r11+8], rbx
0x140043ec3  push    rbp
0x140043ec4  push    rsi
0x140043ec5  push    rdi
0x140043ec6  sub     rsp, 40h
0x140043eca  test    dl, dl
0x140043ecc  mov     qword ptr [r11+18h], 0
0x140043ed4  lea     rax, aRegistryMachin_1; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x140043edb  mov     qword ptr [r11+20h], 0
0x140043ee3  mov     dil, dl
0x140043ee6  lea     rsi, aRegistryMachin; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x140043eed  cmovz   rsi, rax
0x140043ef1  lea     r8, [r11+18h]
0x140043ef5  mov     rdx, rsi
0x140043ef8  mov     rbp, rcx
0x140043efb  call    MyRegOpenKeyForRead
0x140043f00  mov     ebx, eax
0x140043f02  test    eax, eax
0x140043f04  jns     short loc_140043F6C
0x140043f06  mov     r8d, 1
0x140043f0c  cmp     dil, r8b
0x140043f0f  jnz     short loc_140043F50
0x140043f11  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140043f18  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140043f1f  jz      loc_140044027
0x140043f25  lea     r9d, [r8+1Ch]
0x140043f29  mov     rcx, cs:WPP_GLOBAL_Control
0x140043f30  mov     dl, 4
0x140043f32  mov     dword ptr [rsp+58h+var_30], eax
0x140043f36  lea     rax, WPP_5169c4c8089132207a438b4341aed5b6_Traceguids
0x140043f3d  mov     [rsp+58h+var_38], rax
0x140043f42  mov     rcx, [rcx+40h]
0x140043f46  call    WPP_RECORDER_SF_d
0x140043f4b  jmp     loc_140044027
0x140043f50  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140043f57  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140043f5e  jz      loc_140044027
0x140043f64  mov     r9d, 1Eh
0x140043f6a  jmp     short loc_140043F29
0x140043f6c  mov     rcx, [rsp+58h+Handle]; KeyHandle
0x140043f71  lea     r8, [rsp+58h+P]
0x140043f76  lea     rdx, aCurrentconfigu; "CurrentConfiguration"
0x140043f7d  call    MyRegQueryString
0x140043f82  mov     rdi, [rsp+58h+P]
0x140043f87  mov     ebx, eax
0x140043f89  test    eax, eax
0x140043f8b  jns     short loc_140043FC0
0x140043f8d  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140043f94  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140043f9b  jz      short loc_140044011
0x140043f9d  mov     rcx, cs:WPP_GLOBAL_Control
0x140043fa4  mov     r9d, 1Fh
0x140043faa  mov     dword ptr [rsp+58h+var_28], eax
0x140043fae  mov     dl, 3
0x140043fb0  mov     [rsp+58h+var_30], rsi
0x140043fb5  mov     rcx, [rcx+40h]
0x140043fb9  call    WPP_RECORDER_SF_Sd
0x140043fbe  jmp     short loc_140044011
0x140043fc0  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140043fc7  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140043fce  jz      short loc_140043FEA
0x140043fd0  mov     rcx, cs:WPP_GLOBAL_Control
0x140043fd7  mov     [rsp+58h+var_28], rdi
0x140043fdc  mov     [rsp+58h+var_30], rsi
0x140043fe1  mov     rcx, [rcx+40h]
0x140043fe5  call    WPP_RECORDER_SF_SS
0x140043fea  mov     rcx, [rsp+58h+Handle]; Handle
0x140043fef  call    cs:__imp_ZwClose
0x140043ff6  nop     dword ptr [rax+rax+00h]
0x140043ffb  mov     rdx, rdi
0x140043ffe  mov     [rsp+58h+Handle], 0
0x140044007  mov     rcx, rbp
0x14004400a  call    CheckUSBFnConfiguration
0x14004400f  mov     ebx, eax
0x140044011  test    rdi, rdi
0x140044014  jz      short loc_140044027
0x140044016  xor     edx, edx; Tag
0x140044018  mov     rcx, rdi; P
0x14004401b  call    cs:__imp_ExFreePoolWithTag
0x140044022  nop     dword ptr [rax+rax+00h]
0x140044027  mov     rcx, [rsp+58h+Handle]; Handle
0x14004402c  test    rcx, rcx
0x14004402f  jz      short loc_14004403D
0x140044031  call    cs:__imp_ZwClose
0x140044038  nop     dword ptr [rax+rax+00h]
0x14004403d  mov     eax, ebx
0x14004403f  mov     rbx, [rsp+58h+arg_0]
0x140044044  add     rsp, 40h
0x140044048  pop     rdi
0x140044049  pop     rsi
0x14004404a  pop     rbp
0x14004404b  retn
```
