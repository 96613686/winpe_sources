# WcProcessWciLinkBounce

- ea: `0x140026cec`
- end: `0x140026e28`
- name: `WcProcessWciLinkBounce`
- size: `316`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140025270`

## callees

- `0x1400016f0`
- `0x1400048a4`
- `0x140004b0c`
- `0x140014ad4`
- `0x140026cec`
- `0x14002eea4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140026d36`
- `ntoskrnl!RtlInitUnicodeString` at `0x140026d36`

## string_xrefs

- `0x140026d7d`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140026de0`: `onecore\base\fs\wci\wcifs\create.c`

## pseudocode

```c
__int64 __fastcall WcProcessWciLinkBounce(PFLT_CALLBACK_DATA Data, __int64 a2, __int64 a3)
{
  __int64 UnionContext; // rax
  int v6; // edx
  int v7; // ebx
  __int64 v8; // rdi
  int v9; // ecx
  int v10; // edx
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-38h] BYREF

  DestinationString = 0;
  UnionContext = WcGetUnionContext(Data, a2, a3);
  v7 = 0;
  v8 = UnionContext;
  if ( UnionContext )
  {
    if ( *(_DWORD *)(UnionContext + 40) == Data->IoStatus.Information )
    {
      v9 = *(_DWORD *)(UnionContext + 24);
      if ( v9 == 2 )
      {
        RtlInitUnicodeString(&DestinationString, 0);
        v7 = WcRedirectCallbackData(Data);
        if ( v7 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v10) = 2;
          WPP_RECORDER_SF_sDZd(
            wil_details_featureDescriptors_a->DeviceExtension,
            v10,
            5,
            32,
            (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
            189,
            a3 + 88,
            v7);
        }
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v6) = 3;
        WPP_RECORDER_SF_sDdZ(
          wil_details_featureDescriptors_a->DeviceExtension,
          v6,
          5,
          33,
          (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
          199,
          v9,
          a3 + 88);
      }
    }
    WcReleaseUnionContext(v8);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140026cec  push    rbx
0x140026cee  push    rbp
0x140026cef  push    rsi
0x140026cf0  push    rdi
0x140026cf1  sub     rsp, 68h
0x140026cf5  xorps   xmm0, xmm0
0x140026cf8  mov     rbp, r8
0x140026cfb  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x140026d00  mov     rsi, rcx
0x140026d03  call    WcGetUnionContext
0x140026d08  xor     ebx, ebx
0x140026d0a  mov     rdi, rax
0x140026d0d  test    rax, rax
0x140026d10  jz      loc_140026E1C
0x140026d16  mov     eax, [rax+28h]
0x140026d19  cmp     rax, [rsi+20h]
0x140026d1d  jnz     loc_140026E14
0x140026d23  mov     ecx, [rdi+18h]
0x140026d26  cmp     ecx, 2
0x140026d29  jnz     loc_140026DBB
0x140026d2f  xor     edx, edx; SourceString
0x140026d31  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x140026d36  call    cs:__imp_RtlInitUnicodeString
0x140026d3d  nop     dword ptr [rax+rax+00h]
0x140026d42  lea     r8, [rsp+88h+DestinationString]
0x140026d47  mov     rdx, rdi
0x140026d4a  mov     rcx, rsi; Data
0x140026d4d  call    WcRedirectCallbackData
0x140026d52  mov     ebx, eax
0x140026d54  test    eax, eax
0x140026d56  jns     loc_140026E14
0x140026d5c  lea     rax, WPP_RECORDER_INITIALIZED
0x140026d63  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140026d6a  jz      loc_140026E14
0x140026d70  mov     dword ptr [rsp+88h+var_48], ebx
0x140026d74  lea     rcx, [rbp+58h]
0x140026d78  mov     [rsp+88h+var_50], rcx
0x140026d7d  lea     rax, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140026d84  mov     rcx, cs:wil_details_featureDescriptors_a
0x140026d8b  mov     r9d, 20h ; ' '
0x140026d91  mov     [rsp+88h+var_58], 5BDh
0x140026d99  mov     dl, 2
0x140026d9b  mov     [rsp+88h+var_60], rax
0x140026da0  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140026da7  mov     [rsp+88h+var_68], rax
0x140026dac  mov     rcx, [rcx+40h]
0x140026db0  lea     r8d, [r9-1Bh]
0x140026db4  call    WPP_RECORDER_SF_sDZd
0x140026db9  jmp     short loc_140026E14
0x140026dbb  lea     rax, WPP_RECORDER_INITIALIZED
0x140026dc2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140026dc9  jz      short loc_140026E14
0x140026dcb  lea     rax, [rbp+58h]
0x140026dcf  mov     r9d, 21h ; '!'
0x140026dd5  mov     [rsp+88h+var_48], rax
0x140026dda  mov     dl, 3
0x140026ddc  mov     dword ptr [rsp+88h+var_50], ecx
0x140026de0  lea     rax, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140026de7  mov     rcx, cs:wil_details_featureDescriptors_a
0x140026dee  mov     [rsp+88h+var_58], 5C7h
0x140026df6  lea     r8d, [r9-1Ch]
0x140026dfa  mov     [rsp+88h+var_60], rax
0x140026dff  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140026e06  mov     [rsp+88h+var_68], rax
0x140026e0b  mov     rcx, [rcx+40h]
0x140026e0f  call    WPP_RECORDER_SF_sDdZ
0x140026e14  mov     rcx, rdi
0x140026e17  call    WcReleaseUnionContext
0x140026e1c  mov     eax, ebx
0x140026e1e  add     rsp, 68h
0x140026e22  pop     rdi
0x140026e23  pop     rsi
0x140026e24  pop     rbp
0x140026e25  pop     rbx
0x140026e26  retn
```
