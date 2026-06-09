# filterDoInternalRequest

- ea: `0x140007d58`
- end: `0x140007f63`
- name: `filterDoInternalRequest`
- size: `523`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: ``

## callers

- `0x140001174`
- `0x140003b7c`
- `0x14000745c`
- `0x14000aef0`
- `0x14000d3a0`
- `0x14000ea3c`

## callees

- `0x140007d58`
- `0x14000cd98`
- `0x14000d8ec`
- `0x14000d91c`
- `0x14000f110`
- `0x14000f500`

## import_xrefs

- `NDIS!NdisFOidRequest` at `0x140007e24`
- `NDIS!NdisFOidRequest` at `0x140007e24`
- `NDIS!NdisInitializeEvent` at `0x140007dd0`
- `NDIS!NdisInitializeEvent` at `0x140007dd0`
- `NDIS!NdisWaitEvent` at `0x140007e3f`
- `NDIS!NdisWaitEvent` at `0x140007e3f`

## pseudocode

```c
__int64 __fastcall filterDoInternalRequest(
        __int64 a1,
        unsigned int a2,
        int a3,
        __int64 a4,
        unsigned int a5,
        unsigned int a6,
        __int64 a7,
        unsigned int *a8)
{
  void *v12; // rcx
  unsigned int v13; // edi
  unsigned int v15; // eax
  unsigned int v16; // eax
  _BYTE OidRequest[280]; // [rsp+20h] [rbp-E0h] BYREF

  memset(OidRequest, 0, sizeof(OidRequest));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0xEDu,
      (__int64)WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  memset(OidRequest, 0, 0xF8u);
  NdisInitializeEvent((PNDIS_EVENT)&OidRequest[248]);
  *(_DWORD *)OidRequest = 15466902;
  *(_DWORD *)&OidRequest[4] = a2;
  if ( a2 <= 1 )
    goto LABEL_3;
  if ( a2 == 12 )
  {
    *(_QWORD *)&OidRequest[52] = a6;
LABEL_3:
    *(_DWORD *)&OidRequest[48] = a5;
    *(_QWORD *)&OidRequest[40] = a4;
    *(_DWORD *)&OidRequest[32] = a3;
    goto LABEL_4;
  }
  TraceAssert((int)"FALSE", (__int64)"onecoreuap\\net\\vwifi\\filter\\filter.c", 4232);
LABEL_4:
  v12 = *(void **)(a1 + 128);
  *(_QWORD *)&OidRequest[16] = 1380341590;
  v13 = NdisFOidRequest(v12, (PNDIS_OID_REQUEST)OidRequest);
  if ( v13 == 259 )
  {
    NdisWaitEvent((PNDIS_EVENT)&OidRequest[248], 0);
    v13 = *(_DWORD *)&OidRequest[272];
  }
  if ( v13 )
  {
    if ( !a2 )
      *a8 = *(_DWORD *)&OidRequest[56];
    goto LABEL_9;
  }
  if ( a2 < 2 )
  {
    v16 = *(_DWORD *)&OidRequest[52];
    *a8 = *(_DWORD *)&OidRequest[52];
  }
  else
  {
    if ( a2 == 12 )
    {
      v15 = *(_DWORD *)&OidRequest[60];
      *a8 = *(_DWORD *)&OidRequest[60];
      if ( v15 > a6 )
        *a8 = a6;
      goto LABEL_9;
    }
    v16 = *a8;
  }
  if ( v16 > a5 )
    *a8 = a5;
LABEL_9:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0xEEu,
      (__int64)WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids,
      v13);
  return v13;
}

```

## disassembly

```asm
0x140007d58  push    rbp
0x140007d5a  push    rbx
0x140007d5b  push    rsi
0x140007d5c  push    rdi
0x140007d5d  push    r12
0x140007d5f  push    r13
0x140007d61  push    r14
0x140007d63  push    r15
0x140007d65  lea     rbp, [rsp-58h]
0x140007d6a  sub     rsp, 158h
0x140007d71  mov     rax, cs:__security_cookie
0x140007d78  xor     rax, rsp
0x140007d7b  mov     [rbp+90h+var_50], rax
0x140007d7f  mov     rbx, [rbp+90h+arg_38]
0x140007d86  mov     r12d, r8d
0x140007d89  mov     esi, edx
0x140007d8b  mov     r13, rcx
0x140007d8e  xor     edx, edx; Val
0x140007d90  lea     rcx, [rsp+190h+OidRequest]; void *
0x140007d95  mov     r8d, 118h; Size
0x140007d9b  mov     rdi, r9
0x140007d9e  call    memset
0x140007da3  mov     rcx, cs:WPP_GLOBAL_Control
0x140007daa  lea     rax, WPP_GLOBAL_Control
0x140007db1  cmp     rcx, rax
0x140007db4  jnz     loc_140007E94
0x140007dba  xor     edx, edx; Val
0x140007dbc  lea     rcx, [rsp+190h+OidRequest]; void *
0x140007dc1  mov     r8d, 0F8h; Size
0x140007dc7  call    memset
0x140007dcc  lea     rcx, [rbp+90h+Event]; Event
0x140007dd0  call    cs:__imp_NdisInitializeEvent
0x140007dd7  nop     dword ptr [rax+rax+00h]
0x140007ddc  mov     r15d, [rbp+90h+arg_28]
0x140007de3  mov     ecx, esi
0x140007de5  mov     r14d, [rbp+90h+arg_20]
0x140007dec  mov     dword ptr [rsp+190h+OidRequest.Header.Type], 0EC0196h
0x140007df4  mov     [rsp+190h+OidRequest.RequestType], esi
0x140007df8  test    esi, esi
0x140007dfa  jnz     loc_140007EFF
0x140007e00  mov     dword ptr [rsp+190h+OidRequest.DATA+10h], r14d
0x140007e05  mov     qword ptr [rsp+190h+OidRequest.DATA+8], rdi
0x140007e0a  mov     dword ptr [rsp+190h+OidRequest.DATA], r12d
0x140007e0f  mov     rcx, [r13+80h]; NdisFilterHandle
0x140007e16  lea     rdx, [rsp+190h+OidRequest]; OidRequest
0x140007e1b  mov     [rsp+190h+OidRequest.RequestId], 52465756h
0x140007e24  call    cs:__imp_NdisFOidRequest
0x140007e2b  nop     dword ptr [rax+rax+00h]
0x140007e30  mov     edi, eax
0x140007e32  cmp     eax, 103h
0x140007e37  jnz     short loc_140007E4E
0x140007e39  xor     edx, edx; MsToWait
0x140007e3b  lea     rcx, [rbp+90h+Event]; Event
0x140007e3f  call    cs:__imp_NdisWaitEvent
0x140007e46  nop     dword ptr [rax+rax+00h]
0x140007e4b  mov     edi, [rbp+90h+var_60]
0x140007e4e  test    edi, edi
0x140007e50  jz      loc_140007EDA
0x140007e56  test    esi, esi
0x140007e58  jz      loc_140007F58
0x140007e5e  mov     rcx, cs:WPP_GLOBAL_Control
0x140007e65  lea     rax, WPP_GLOBAL_Control
0x140007e6c  cmp     rcx, rax
0x140007e6f  jnz     short loc_140007EB9
0x140007e71  mov     eax, edi
0x140007e73  mov     rcx, [rbp+90h+var_50]
0x140007e77  xor     rcx, rsp; StackCookie
0x140007e7a  call    __security_check_cookie
0x140007e7f  add     rsp, 158h
0x140007e86  pop     r15
0x140007e88  pop     r14
0x140007e8a  pop     r13
0x140007e8c  pop     r12
0x140007e8e  pop     rdi
0x140007e8f  pop     rsi
0x140007e90  pop     rbx
0x140007e91  pop     rbp
0x140007e92  retn
0x140007e94  mov     eax, [rcx+2Ch]
0x140007e97  test    al, 20h
0x140007e99  jz      loc_140007DBA
0x140007e9f  mov     rcx, [rcx+18h]
0x140007ea3  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140007eaa  mov     edx, 0EDh
0x140007eaf  call    WPP_SF_
0x140007eb4  jmp     loc_140007DBA
0x140007eb9  mov     eax, [rcx+2Ch]
0x140007ebc  test    al, 20h
0x140007ebe  jz      short loc_140007E71
0x140007ec0  mov     rcx, [rcx+18h]
0x140007ec4  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140007ecb  mov     edx, 0EEh
0x140007ed0  mov     r9d, edi
0x140007ed3  call    WPP_SF_d
0x140007ed8  jmp     short loc_140007E71
0x140007eda  cmp     esi, 1
0x140007edd  jz      short loc_140007F1F
0x140007edf  test    esi, esi
0x140007ee1  jz      short loc_140007F1F
0x140007ee3  cmp     esi, 0Ch
0x140007ee6  jnz     short loc_140007F36
0x140007ee8  mov     eax, dword ptr [rsp+190h+OidRequest.DATA+1Ch]
0x140007eec  mov     [rbx], eax
0x140007eee  cmp     eax, r15d
0x140007ef1  jbe     loc_140007E5E
0x140007ef7  mov     [rbx], r15d
0x140007efa  jmp     loc_140007E5E
0x140007eff  sub     ecx, 1
0x140007f02  jz      loc_140007E00
0x140007f08  cmp     ecx, 0Bh
0x140007f0b  jnz     short loc_140007F3A
0x140007f0d  mov     dword ptr [rsp+190h+OidRequest.DATA+18h], 0
0x140007f15  mov     dword ptr [rsp+190h+OidRequest.DATA+14h], r15d
0x140007f1a  jmp     loc_140007E00
0x140007f1f  mov     eax, dword ptr [rsp+190h+OidRequest.DATA+14h]
0x140007f23  mov     [rbx], eax
0x140007f25  cmp     eax, r14d
0x140007f28  jbe     loc_140007E5E
0x140007f2e  mov     [rbx], r14d
0x140007f31  jmp     loc_140007E5E
0x140007f36  mov     eax, [rbx]
0x140007f38  jmp     short loc_140007F25
0x140007f3a  mov     r8d, 1088h
0x140007f40  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x140007f47  lea     rcx, aFalse; "FALSE"
0x140007f4e  call    TraceAssert
0x140007f53  jmp     loc_140007E0F
0x140007f58  mov     eax, dword ptr [rsp+190h+OidRequest.DATA+18h]
0x140007f5c  mov     [rbx], eax
0x140007f5e  jmp     loc_140007E5E
```
