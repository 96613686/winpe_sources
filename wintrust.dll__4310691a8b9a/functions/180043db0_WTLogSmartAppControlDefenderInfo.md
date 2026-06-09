# WTLogSmartAppControlDefenderInfo

- ea: `0x180043db0`
- end: `0x180043f64`
- name: `WTLogSmartAppControlDefenderInfo`
- size: `436`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x18002640c`
- `0x18002d598`
- `0x180043db0`
- `0x18004de6a`
- `0x18004deb0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180043f38`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180043f38`
- `ntdll!RtlInitUnicodeString` at `0x180043e38`
- `ntdll!RtlInitUnicodeString` at `0x180043e38`

## pseudocode

```c
__int64 __fastcall WTLogSmartAppControlDefenderInfo(__int64 a1, const GUID *a2, const WCHAR *a3)
{
  __int64 result; // rax
  __int16 v7; // [rsp+30h] [rbp-D0h] BYREF
  REGHANDLE RegHandle; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v9[2]; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-A0h] BYREF
  char v12; // [rsp+70h] [rbp-90h] BYREF
  __int64 v13; // [rsp+80h] [rbp-80h]
  __int64 v14; // [rsp+88h] [rbp-78h]
  __int64 v15; // [rsp+90h] [rbp-70h]
  __int64 v16; // [rsp+98h] [rbp-68h]
  __int64 v17; // [rsp+A0h] [rbp-60h]
  __int64 v18; // [rsp+A8h] [rbp-58h]
  __int64 v19; // [rsp+B0h] [rbp-50h]
  __int64 v20; // [rsp+B8h] [rbp-48h]
  __int64 v21; // [rsp+C0h] [rbp-40h]
  __int64 v22; // [rsp+C8h] [rbp-38h]
  __int64 v23; // [rsp+D0h] [rbp-30h]
  __int64 v24; // [rsp+D8h] [rbp-28h]
  __int64 v25; // [rsp+E0h] [rbp-20h]
  __int64 v26; // [rsp+E8h] [rbp-18h]
  __int64 v27; // [rsp+F0h] [rbp-10h]
  __int64 v28; // [rsp+F8h] [rbp-8h]
  __int64 v29; // [rsp+100h] [rbp+0h]
  __int64 v30; // [rsp+108h] [rbp+8h]
  __int64 v31; // [rsp+110h] [rbp+10h]
  __int64 v32; // [rsp+118h] [rbp+18h]
  __int64 v33; // [rsp+120h] [rbp+20h]
  __int64 v34; // [rsp+128h] [rbp+28h]

  v9[0] = 0x20000;
  v7 = 0;
  v9[1] = &qword_180056E08;
  DestinationString = 0;
  RegHandle = 0;
  result = GetEventHandle(&RegHandle);
  if ( (int)result >= 0 )
  {
    memset_0(&UserData, 0, 0xD0u);
    RtlInitUnicodeString(&DestinationString, a3);
    EventDataWriteUnicodeString(
      (unsigned int)&UserData,
      (unsigned int)&v12,
      (unsigned int)v9,
      (unsigned int)&DestinationString,
      (__int64)&v7);
    v13 = *(_QWORD *)(a1 + 160);
    v27 = a1 + 80;
    v15 = a1 + 208;
    v17 = a1 + 96;
    v19 = a1 + 100;
    v21 = a1 + 104;
    v23 = a1 + 128;
    v25 = a1 + 84;
    v29 = a1 + 88;
    v31 = a1 + 92;
    v14 = 32;
    v33 = a1 + 64;
    v16 = 4;
    v18 = 4;
    v20 = 4;
    v22 = 16;
    v24 = 8;
    v26 = 4;
    v28 = 4;
    v30 = 4;
    v32 = 4;
    v34 = 4;
    EventWriteTransfer(RegHandle, &SmartAppControlBlockDetails, a2, 0, 0xDu, &UserData);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180043db0  mov     [rsp-8+arg_0], rbx
0x180043db5  mov     [rsp-8+arg_18], rsi
0x180043dba  push    rbp
0x180043dbb  push    rdi
0x180043dbc  push    r14
0x180043dbe  lea     rbp, [rsp-40h]
0x180043dc3  sub     rsp, 140h
0x180043dca  mov     rax, cs:__security_cookie
0x180043dd1  xor     rax, rsp
0x180043dd4  mov     [rbp+50h+var_20], rax
0x180043dd8  mov     rbx, rcx
0x180043ddb  mov     [rsp+150h+var_110], 20000h
0x180043de4  xor     r14d, r14d
0x180043de7  lea     rax, qword_180056E08
0x180043dee  xorps   xmm0, xmm0
0x180043df1  mov     [rsp+150h+var_120], r14w
0x180043df7  lea     rcx, [rsp+150h+RegHandle]; unsigned __int64 *
0x180043dfc  mov     [rsp+150h+var_108], rax
0x180043e01  movups  xmmword ptr [rsp+150h+DestinationString.Length], xmm0
0x180043e06  mov     [rsp+150h+RegHandle], r14
0x180043e0b  mov     rsi, r8
0x180043e0e  mov     rdi, rdx
0x180043e11  call    ?GetEventHandle@@YAJPEA_K@Z; GetEventHandle(unsigned __int64 *)
0x180043e16  test    eax, eax
0x180043e18  js      loc_180043F40
0x180043e1e  xor     edx, edx; Val
0x180043e20  lea     rcx, [rsp+150h+var_F0]; void *
0x180043e25  mov     r8d, 0D0h; Size
0x180043e2b  call    memset_0
0x180043e30  mov     rdx, rsi; SourceString
0x180043e33  lea     rcx, [rsp+150h+DestinationString]; DestinationString
0x180043e38  call    cs:__imp_RtlInitUnicodeString
0x180043e3e  lea     rax, [rsp+150h+var_120]
0x180043e43  lea     r9, [rsp+150h+DestinationString]
0x180043e48  mov     qword ptr [rsp+150h+UserDataCount], rax
0x180043e4d  lea     r8, [rsp+150h+var_110]
0x180043e52  lea     rdx, [rsp+150h+var_E0]
0x180043e57  lea     rcx, [rsp+150h+var_F0]
0x180043e5c  call    EventDataWriteUnicodeString
0x180043e61  mov     rcx, [rsp+150h+RegHandle]; RegHandle
0x180043e66  lea     rdx, [rbx+50h]
0x180043e6a  mov     rax, [rdx+50h]
0x180043e6e  xor     r9d, r9d; RelatedActivityId
0x180043e71  mov     [rbp+50h+var_D0], rax
0x180043e75  mov     r8, rdi; ActivityId
0x180043e78  lea     rax, [rbx+0D0h]
0x180043e7f  mov     [rbp+50h+var_60], rdx
0x180043e83  mov     [rbp+50h+var_C0], rax
0x180043e87  lea     rax, [rdx+10h]
0x180043e8b  mov     [rbp+50h+var_B0], rax
0x180043e8f  lea     rax, [rdx+14h]
0x180043e93  mov     [rbp+50h+var_A0], rax
0x180043e97  lea     rax, [rdx+18h]
0x180043e9b  mov     [rbp+50h+var_90], rax
0x180043e9f  lea     rax, [rdx+30h]
0x180043ea3  mov     [rbp+50h+var_80], rax
0x180043ea7  lea     rax, [rdx+4]
0x180043eab  mov     [rbp+50h+var_70], rax
0x180043eaf  lea     rax, [rdx+8]
0x180043eb3  mov     [rbp+50h+var_50], rax
0x180043eb7  lea     rax, [rdx+0Ch]
0x180043ebb  mov     [rbp+50h+var_40], rax
0x180043ebf  lea     rdx, SmartAppControlBlockDetails; EventDescriptor
0x180043ec6  lea     rax, [rbx+40h]
0x180043eca  mov     [rbp+50h+var_C8], 20h ; ' '
0x180043ed2  mov     [rbp+50h+var_30], rax
0x180043ed6  lea     rax, [rsp+150h+var_F0]
0x180043edb  mov     [rsp+150h+UserData], rax; UserData
0x180043ee0  mov     [rsp+150h+UserDataCount], 0Dh; UserDataCount
0x180043ee8  mov     [rbp+50h+var_B8], 4
0x180043ef0  mov     [rbp+50h+var_A8], 4
0x180043ef8  mov     [rbp+50h+var_98], 4
0x180043f00  mov     [rbp+50h+var_88], 10h
0x180043f08  mov     [rbp+50h+var_78], 8
0x180043f10  mov     [rbp+50h+var_68], 4
0x180043f18  mov     [rbp+50h+var_58], 4
0x180043f20  mov     [rbp+50h+var_48], 4
0x180043f28  mov     [rbp+50h+var_38], 4
0x180043f30  mov     [rbp+50h+var_28], 4
0x180043f38  call    cs:__imp_EventWriteTransfer
0x180043f3e  xor     eax, eax
0x180043f40  mov     rcx, [rbp+50h+var_20]
0x180043f44  xor     rcx, rsp; StackCookie
0x180043f47  call    __security_check_cookie
0x180043f4c  lea     r11, [rsp+150h+var_10]
0x180043f54  mov     rbx, [r11+20h]
0x180043f58  mov     rsi, [r11+38h]
0x180043f5c  mov     rsp, r11
0x180043f5f  pop     r14
0x180043f61  pop     rdi
0x180043f62  pop     rbp
0x180043f63  retn
```
