# WldpIsDetachedSignatureBlobTrusted(uchar const *,_LARGE_INTEGER,uchar const *,ulong,ushort const *,void *,ulong *)

- ea: `0x18002d030`
- end: `0x18002d221`
- name: `?WldpIsDetachedSignatureBlobTrusted@@YAJPEBET_LARGE_INTEGER@@0KPEBGPEAXPEAK@Z`
- size: `497`
- prototype: `__int64 __fastcall(const unsigned __int8 *, union _LARGE_INTEGER, const unsigned __int8 *, int, const unsigned __int16 *, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18002f648`

## callees

- `0x18001898c`
- `0x18001bb98`
- `0x180021ec0`
- `0x180022a10`
- `0x18002d030`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002d195`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002d195`
- `WINTRUST!WinVerifyTrust` at `0x18002d14b`
- `WINTRUST!WinVerifyTrust` at `0x18002d14b`
- `WINTRUST!WTConfigCiFreePrivateData` at `0x18002d1f6`
- `WINTRUST!WTConfigCiFreePrivateData` at `0x18002d1f6`
- `WINTRUST!WTLogConfigCiScriptEvent2` at `0x18002d1c5`
- `WINTRUST!WTLogConfigCiScriptEvent2` at `0x18002d1c5`
- `WINTRUST!WTLogConfigCiSignerEvent` at `0x18002d1e1`
- `WINTRUST!WTLogConfigCiSignerEvent` at `0x18002d1e1`

## pseudocode

```c
__int64 __fastcall WldpIsDetachedSignatureBlobTrusted(
        const unsigned __int8 *a1,
        union _LARGE_INTEGER a2,
        const unsigned __int8 *a3,
        int a4,
        const unsigned __int16 *a5,
        void *a6,
        unsigned int *a7)
{
  unsigned int v11; // ebx
  unsigned int v12; // r8d
  int v13; // ecx
  _BYTE v15[8]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v16[2]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v17; // [rsp+50h] [rbp-B0h]
  _QWORD v18[2]; // [rsp+58h] [rbp-A8h] BYREF
  int v19; // [rsp+68h] [rbp-98h]
  int v20; // [rsp+6Ch] [rbp-94h]
  const unsigned __int8 *v21; // [rsp+70h] [rbp-90h]
  int pWVTData; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v23; // [rsp+88h] [rbp-78h]
  int v24; // [rsp+98h] [rbp-68h]
  int v25; // [rsp+9Ch] [rbp-64h]
  int v26; // [rsp+A0h] [rbp-60h]
  _DWORD *v27; // [rsp+A8h] [rbp-58h]
  int v28; // [rsp+B0h] [rbp-50h]
  __int64 v29; // [rsp+B8h] [rbp-48h]
  int v30; // [rsp+C8h] [rbp-38h]
  __int64 v31; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v32; // [rsp+E8h] [rbp-18h]
  __int128 v33; // [rsp+F8h] [rbp-8h]
  _DWORD *v34; // [rsp+108h] [rbp+8h]
  _DWORD v35[2]; // [rsp+110h] [rbp+10h] BYREF
  int v36; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v37; // [rsp+1E8h] [rbp+E8h]
  void *v38; // [rsp+1F0h] [rbp+F0h]
  GUID ActivityId; // [rsp+200h] [rbp+100h] BYREF

  memset_0(v35, 0, 0xE8u);
  v35[0] = 232;
  memset_0(&pWVTData, 0, 0x58u);
  v31 = 48;
  v32 = 0;
  v33 = 0;
  v16[1] = 2;
  v20 = 0;
  v18[0] = a2.QuadPart;
  v18[1] = a1;
  v19 = a4;
  v21 = a3;
  v17 = v18;
  v16[0] = 16;
  v37 = a5;
  v38 = a6;
  v34 = v35;
  pWVTData = 88;
  v24 = 2;
  v26 = 6;
  v27 = v16;
  v28 = 1;
  v25 = 1;
  v30 = 4224;
  v23 = &v31;
  v11 = WinVerifyTrust(HWND_MESSAGE|0x2LL, (GUID *)&stru_180047D90, &pWVTData);
  if ( IsWvtErrorRecoverable((char *)v11, v15, v12) )
  {
    v13 = HIDWORD(v32);
    *a7 = HIDWORD(v32);
    v35[1] = v13 != 1 ? 0xD0E90002 : 0;
    v36 = v13;
    ActivityId = 0;
    EventActivityIdControl(3u, &ActivityId);
    WTLogConfigCiScriptEvent2(v29, 0, 0, -1, 0, v35, &ActivityId);
    if ( v36 != 1 )
      WTLogConfigCiSignerEvent(v29, &ActivityId, 1, 1);
    WldpFreeStateData(v29);
    v11 = 0;
  }
  WTConfigCiFreePrivateData(v35);
  return v11;
}

```

## disassembly

```asm
0x18002d030  push    rbp
0x18002d032  push    rbx
0x18002d033  push    rsi
0x18002d034  push    rdi
0x18002d035  push    r12
0x18002d037  push    r13
0x18002d039  push    r14
0x18002d03b  push    r15
0x18002d03d  lea     rbp, [rsp-128h]
0x18002d045  sub     rsp, 228h
0x18002d04c  mov     rax, cs:__security_cookie
0x18002d053  xor     rax, rsp
0x18002d056  mov     [rbp+160h+var_50], rax
0x18002d05d  mov     r12d, r9d
0x18002d060  mov     r15, r8
0x18002d063  mov     rbx, rdx
0x18002d066  mov     r14, rcx
0x18002d069  mov     rdi, [rbp+160h+arg_20]
0x18002d070  mov     rsi, [rbp+160h+arg_28]
0x18002d077  mov     r13, [rbp+160h+arg_30]
0x18002d07e  xor     edx, edx; Val
0x18002d080  mov     r8d, 0E8h; Size
0x18002d086  lea     rcx, [rbp+160h+var_150]; void *
0x18002d08a  call    memset_0
0x18002d08f  mov     [rbp+160h+var_150], 0E8h
0x18002d096  xor     edx, edx; Val
0x18002d098  lea     r8d, [rdx+58h]; Size
0x18002d09c  lea     rcx, [rbp+160h+pWVTData]; void *
0x18002d0a0  call    memset_0
0x18002d0a5  mov     [rbp+160h+var_180], 30h ; '0'
0x18002d0ad  xorps   xmm0, xmm0
0x18002d0b0  xor     eax, eax
0x18002d0b2  movups  [rbp+160h+var_178], xmm0
0x18002d0b6  movups  [rbp+160h+var_168], xmm0
0x18002d0ba  lea     ecx, [rax+2]
0x18002d0bd  mov     [rsp+260h+var_214], ecx
0x18002d0c1  movups  [rsp+260h+var_204], xmm0
0x18002d0c6  movups  [rsp+260h+var_204+0Ch], xmm0
0x18002d0cb  mov     [rsp+58h], rbx
0x18002d0d0  mov     qword ptr [rsp+260h+var_204+4], r14
0x18002d0d5  mov     dword ptr [rsp+260h+var_204+0Ch], r12d
0x18002d0da  mov     [rsp+260h+var_1F0], r15
0x18002d0df  lea     rax, [rsp+260h+var_208]
0x18002d0e4  mov     [rsp+260h+var_210], rax
0x18002d0e9  mov     [rsp+260h+var_218], 10h
0x18002d0f1  mov     [rbp+160h+var_78], rdi
0x18002d0f8  mov     [rbp+160h+var_70], rsi
0x18002d0ff  lea     rax, [rbp+160h+var_150]
0x18002d103  mov     [rbp+160h+var_158], rax
0x18002d107  mov     [rbp+160h+pWVTData], 58h ; 'X'
0x18002d10e  mov     [rbp+160h+var_1C8], ecx
0x18002d111  mov     [rbp+160h+var_1C0], 6
0x18002d118  lea     rax, [rsp+260h+var_218]
0x18002d11d  mov     [rbp+160h+var_1B8], rax
0x18002d121  lea     edi, [rcx-1]
0x18002d124  mov     [rbp+160h+var_1B0], edi
0x18002d127  mov     [rbp+160h+var_1C4], edi
0x18002d12a  mov     [rbp+160h+var_198], 1080h
0x18002d131  lea     rax, [rbp+160h+var_180]
0x18002d135  mov     [rbp+160h+var_1D8], rax
0x18002d139  lea     r8, [rbp+160h+pWVTData]; pWVTData
0x18002d13d  lea     rdx, stru_180047D90; pgActionID
0x18002d144  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002d148  mov     rcx, rsi; hwnd
0x18002d14b  call    cs:__imp_WinVerifyTrust
0x18002d151  mov     ebx, eax
0x18002d153  lea     rdx, [rsp+260h+var_220]
0x18002d158  mov     ecx, eax
0x18002d15a  call    IsWvtErrorRecoverable
0x18002d15f  test    al, al
0x18002d161  jz      loc_18002D1F2
0x18002d167  mov     ecx, dword ptr [rbp+160h+var_178+0Ch]
0x18002d16a  mov     [r13+0], ecx
0x18002d16e  mov     eax, ecx
0x18002d170  sub     eax, edi
0x18002d172  neg     eax
0x18002d174  sbb     eax, eax
0x18002d176  and     eax, 0D0E90002h
0x18002d17b  mov     [rbp+160h+var_14C], eax
0x18002d17e  mov     [rbp+160h+var_148], ecx
0x18002d181  xorps   xmm0, xmm0
0x18002d184  movups  xmmword ptr [rbp+160h+ActivityId.Data1], xmm0
0x18002d18b  lea     rdx, [rbp+160h+ActivityId]; ActivityId
0x18002d192  lea     ecx, [rdi+2]; ControlCode
0x18002d195  call    cs:__imp_EventActivityIdControl
0x18002d19b  lea     rax, [rbp+160h+ActivityId]
0x18002d1a2  mov     [rsp+260h+var_230], rax
0x18002d1a7  lea     rax, [rbp+160h+var_150]
0x18002d1ab  mov     [rsp+260h+var_238], rax
0x18002d1b0  mov     [rsp+260h+var_240], 0
0x18002d1b9  mov     r9, rsi
0x18002d1bc  xor     r8d, r8d
0x18002d1bf  xor     edx, edx
0x18002d1c1  mov     rcx, [rbp+160h+var_1A8]
0x18002d1c5  call    cs:__imp_WTLogConfigCiScriptEvent2
0x18002d1cb  cmp     [rbp+160h+var_148], edi
0x18002d1ce  jz      short loc_18002D1E7
0x18002d1d0  mov     r9d, edi
0x18002d1d3  mov     r8d, edi
0x18002d1d6  lea     rdx, [rbp+160h+ActivityId]
0x18002d1dd  mov     rcx, [rbp+160h+var_1A8]
0x18002d1e1  call    cs:__imp_WTLogConfigCiSignerEvent
0x18002d1e7  mov     rcx, [rbp+160h+var_1A8]
0x18002d1eb  call    WldpFreeStateData
0x18002d1f0  xor     ebx, ebx
0x18002d1f2  lea     rcx, [rbp+160h+var_150]
0x18002d1f6  call    cs:__imp_WTConfigCiFreePrivateData
0x18002d1fc  mov     eax, ebx
0x18002d1fe  mov     rcx, [rbp+160h+var_50]
0x18002d205  xor     rcx, rsp; StackCookie
0x18002d208  call    __security_check_cookie
0x18002d20d  add     rsp, 228h
0x18002d214  pop     r15
0x18002d216  pop     r14
0x18002d218  pop     r13
0x18002d21a  pop     r12
0x18002d21c  pop     rdi
0x18002d21d  pop     rsi
0x18002d21e  pop     rbx
0x18002d21f  pop     rbp
0x18002d220  retn
```
