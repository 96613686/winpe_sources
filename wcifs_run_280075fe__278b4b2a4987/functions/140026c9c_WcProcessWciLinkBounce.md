# WcProcessWciLinkBounce

- ea: `0x140026c9c`
- end: `0x140026dd8`
- name: `WcProcessWciLinkBounce`
- size: `316`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140025220`

## callees

- `0x1400016f0`
- `0x1400048a4`
- `0x140004b0c`
- `0x140014ad4`
- `0x140026c9c`
- `0x14002ee54`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140026ce6`
- `ntoskrnl!RtlInitUnicodeString` at `0x140026ce6`

## string_xrefs

- `0x140026d2d`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140026d90`: `onecore\base\fs\wci\wcifs\create.c`

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
        v7 = WcRedirectCallbackData(Data, v8, &DestinationString);
        if ( v7 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v10) = 2;
          WPP_RECORDER_SF_sDZd(
            WPP_GLOBAL_Control->DeviceExtension,
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
          WPP_GLOBAL_Control->DeviceExtension,
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
0x140026c9c  push    rbx
0x140026c9e  push    rbp
0x140026c9f  push    rsi
0x140026ca0  push    rdi
0x140026ca1  sub     rsp, 68h
0x140026ca5  xorps   xmm0, xmm0
0x140026ca8  mov     rbp, r8
0x140026cab  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x140026cb0  mov     rsi, rcx
0x140026cb3  call    WcGetUnionContext
0x140026cb8  xor     ebx, ebx
0x140026cba  mov     rdi, rax
0x140026cbd  test    rax, rax
0x140026cc0  jz      loc_140026DCC
0x140026cc6  mov     eax, [rax+28h]
0x140026cc9  cmp     rax, [rsi+20h]
0x140026ccd  jnz     loc_140026DC4
0x140026cd3  mov     ecx, [rdi+18h]
0x140026cd6  cmp     ecx, 2
0x140026cd9  jnz     loc_140026D6B
0x140026cdf  xor     edx, edx; SourceString
0x140026ce1  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x140026ce6  call    cs:__imp_RtlInitUnicodeString
0x140026ced  nop     dword ptr [rax+rax+00h]
0x140026cf2  lea     r8, [rsp+88h+DestinationString]
0x140026cf7  mov     rdx, rdi
0x140026cfa  mov     rcx, rsi; Data
0x140026cfd  call    WcRedirectCallbackData
0x140026d02  mov     ebx, eax
0x140026d04  test    eax, eax
0x140026d06  jns     loc_140026DC4
0x140026d0c  lea     rax, WPP_RECORDER_INITIALIZED
0x140026d13  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140026d1a  jz      loc_140026DC4
0x140026d20  mov     dword ptr [rsp+88h+var_48], ebx
0x140026d24  lea     rcx, [rbp+58h]
0x140026d28  mov     [rsp+88h+var_50], rcx
0x140026d2d  lea     rax, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140026d34  mov     rcx, cs:WPP_GLOBAL_Control
0x140026d3b  mov     r9d, 20h ; ' '
0x140026d41  mov     [rsp+88h+var_58], 5BDh
0x140026d49  mov     dl, 2
0x140026d4b  mov     [rsp+88h+var_60], rax
0x140026d50  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140026d57  mov     [rsp+88h+var_68], rax
0x140026d5c  mov     rcx, [rcx+40h]
0x140026d60  lea     r8d, [r9-1Bh]
0x140026d64  call    WPP_RECORDER_SF_sDZd
0x140026d69  jmp     short loc_140026DC4
0x140026d6b  lea     rax, WPP_RECORDER_INITIALIZED
0x140026d72  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140026d79  jz      short loc_140026DC4
0x140026d7b  lea     rax, [rbp+58h]
0x140026d7f  mov     r9d, 21h ; '!'
0x140026d85  mov     [rsp+88h+var_48], rax
0x140026d8a  mov     dl, 3
0x140026d8c  mov     dword ptr [rsp+88h+var_50], ecx
0x140026d90  lea     rax, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140026d97  mov     rcx, cs:WPP_GLOBAL_Control
0x140026d9e  mov     [rsp+88h+var_58], 5C7h
0x140026da6  lea     r8d, [r9-1Ch]
0x140026daa  mov     [rsp+88h+var_60], rax
0x140026daf  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140026db6  mov     [rsp+88h+var_68], rax
0x140026dbb  mov     rcx, [rcx+40h]
0x140026dbf  call    WPP_RECORDER_SF_sDdZ
0x140026dc4  mov     rcx, rdi
0x140026dc7  call    WcReleaseUnionContext
0x140026dcc  mov     eax, ebx
0x140026dce  add     rsp, 68h
0x140026dd2  pop     rdi
0x140026dd3  pop     rsi
0x140026dd4  pop     rbp
0x140026dd5  pop     rbx
0x140026dd6  retn
```
