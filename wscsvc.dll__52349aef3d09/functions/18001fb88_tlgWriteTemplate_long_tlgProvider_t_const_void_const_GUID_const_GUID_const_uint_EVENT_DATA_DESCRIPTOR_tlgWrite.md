# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18001fb88`
- end: `0x18001fd3a`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@U1@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@333AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `434`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, __int64 **, __int64 **, __int64 **, __int64 **, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180024630`
- `0x18002698c`
- `0x18002fc00`

## callees

- `0x18001fb88`
- `0x18003fc30`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001fd1f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001fd1f`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5,
        __int64 **a6,
        __int64 **a7,
        __int64 **a8,
        __int64 a9,
        __int64 a10)
{
  __int64 v11; // rcx
  __int64 *v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  __int64 *v15; // rdx
  __int64 v16; // rax
  int v17; // eax
  __int64 *v18; // rdx
  __int64 v19; // rax
  int v20; // eax
  __int64 *v21; // rdx
  int v22; // ecx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-81h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int8 *v26; // [rsp+60h] [rbp-59h]
  int v27; // [rsp+68h] [rbp-51h]
  int v28; // [rsp+6Ch] [rbp-4Dh]
  __int64 *v29; // [rsp+70h] [rbp-49h]
  int v30; // [rsp+78h] [rbp-41h]
  int v31; // [rsp+7Ch] [rbp-3Dh]
  __int64 *v32; // [rsp+80h] [rbp-39h]
  int v33; // [rsp+88h] [rbp-31h]
  int v34; // [rsp+8Ch] [rbp-2Dh]
  __int64 *v35; // [rsp+90h] [rbp-29h]
  int v36; // [rsp+98h] [rbp-21h]
  int v37; // [rsp+9Ch] [rbp-1Dh]
  __int64 *v38; // [rsp+A0h] [rbp-19h]
  int v39; // [rsp+A8h] [rbp-11h]
  int v40; // [rsp+ACh] [rbp-Dh]
  __int64 v41; // [rsp+B0h] [rbp-9h]
  __int64 v42; // [rsp+B8h] [rbp-1h]
  __int64 v43; // [rsp+C0h] [rbp+7h]
  __int64 v44; // [rsp+C8h] [rbp+Fh]

  v43 = a10;
  v41 = a9;
  v11 = -1;
  v44 = 4;
  v42 = 4;
  v12 = *a8;
  if ( *a8 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *((_WORD *)v12 + v13) );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v12 = &qword_180045B70;
    v14 = 2;
  }
  v39 = v14;
  v38 = v12;
  v40 = 0;
  v15 = *a7;
  if ( *a7 )
  {
    v16 = -1;
    do
      ++v16;
    while ( *((_WORD *)v15 + v16) );
    v17 = 2 * v16 + 2;
  }
  else
  {
    v15 = &qword_180045B70;
    v17 = 2;
  }
  v36 = v17;
  v35 = v15;
  v37 = 0;
  v18 = *a6;
  if ( *a6 )
  {
    v19 = -1;
    do
      ++v19;
    while ( *((_WORD *)v18 + v19) );
    v20 = 2 * v19 + 2;
  }
  else
  {
    v18 = &qword_180045B70;
    v20 = 2;
  }
  v33 = v20;
  v32 = v18;
  v34 = 0;
  v21 = *a5;
  if ( *a5 )
  {
    do
      ++v11;
    while ( *((_WORD *)v21 + v11) );
    v22 = 2 * v11 + 2;
  }
  else
  {
    v21 = &qword_180045B70;
    v22 = 2;
  }
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180053220;
  v30 = v22;
  v29 = v21;
  v31 = 0;
  UserData.Size = *(unsigned __int16 *)off_180053220;
  v27 = *(unsigned __int16 *)(a2 + 11);
  v26 = a2 + 11;
  UserData.Reserved = 2;
  v28 = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 8u, &UserData);
}

```

## disassembly

```asm
0x18001fb88  push    rbp
0x18001fb8a  lea     rbp, [rsp-27h]
0x18001fb8f  sub     rsp, 0E0h
0x18001fb96  mov     rax, cs:__security_cookie
0x18001fb9d  xor     rax, rsp
0x18001fba0  mov     [rbp+27h+var_10], rax
0x18001fba4  mov     rax, [rbp+27h+arg_48]
0x18001fba8  lea     r10, qword_180045B70
0x18001fbaf  mov     [rbp+27h+var_20], rax
0x18001fbb3  xor     r9d, r9d; RelatedActivityId
0x18001fbb6  mov     rax, [rbp+27h+arg_40]
0x18001fbba  mov     r8, rdx
0x18001fbbd  mov     [rbp+27h+var_30], rax
0x18001fbc1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001fbc5  mov     rax, [rbp+27h+arg_38]
0x18001fbc9  mov     [rbp+27h+var_18], 4
0x18001fbd1  lea     r11d, [r9+2]
0x18001fbd5  mov     [rbp+27h+var_28], 4
0x18001fbdd  mov     rdx, [rax]
0x18001fbe0  test    rdx, rdx
0x18001fbe3  jz      short loc_18001FBFB
0x18001fbe5  mov     rax, rcx
0x18001fbe8  inc     rax
0x18001fbeb  cmp     [rdx+rax*2], r9w
0x18001fbf0  jnz     short loc_18001FBE8
0x18001fbf2  lea     eax, ds:2[rax*2]
0x18001fbf9  jmp     short loc_18001FC01
0x18001fbfb  mov     rdx, r10
0x18001fbfe  mov     eax, r11d
0x18001fc01  mov     [rbp+27h+var_38], eax
0x18001fc04  mov     rax, [rbp+27h+arg_30]
0x18001fc08  mov     [rbp+27h+var_40], rdx
0x18001fc0c  mov     [rbp+27h+var_34], r9d
0x18001fc10  mov     rdx, [rax]
0x18001fc13  test    rdx, rdx
0x18001fc16  jz      short loc_18001FC2E
0x18001fc18  mov     rax, rcx
0x18001fc1b  inc     rax
0x18001fc1e  cmp     [rdx+rax*2], r9w
0x18001fc23  jnz     short loc_18001FC1B
0x18001fc25  lea     eax, ds:2[rax*2]
0x18001fc2c  jmp     short loc_18001FC34
0x18001fc2e  mov     rdx, r10
0x18001fc31  mov     eax, r11d
0x18001fc34  mov     [rbp+27h+var_48], eax
0x18001fc37  mov     rax, [rbp+27h+arg_28]
0x18001fc3b  mov     [rbp+27h+var_50], rdx
0x18001fc3f  mov     [rbp+27h+var_44], r9d
0x18001fc43  mov     rdx, [rax]
0x18001fc46  test    rdx, rdx
0x18001fc49  jz      short loc_18001FC61
0x18001fc4b  mov     rax, rcx
0x18001fc4e  inc     rax
0x18001fc51  cmp     [rdx+rax*2], r9w
0x18001fc56  jnz     short loc_18001FC4E
0x18001fc58  lea     eax, ds:2[rax*2]
0x18001fc5f  jmp     short loc_18001FC67
0x18001fc61  mov     rdx, r10
0x18001fc64  mov     eax, r11d
0x18001fc67  mov     [rbp+27h+var_58], eax
0x18001fc6a  mov     rax, [rbp+27h+arg_20]
0x18001fc6e  mov     [rbp+27h+var_60], rdx
0x18001fc72  mov     [rbp+27h+var_54], r9d
0x18001fc76  mov     rdx, [rax]
0x18001fc79  test    rdx, rdx
0x18001fc7c  jz      short loc_18001FC91
0x18001fc7e  inc     rcx
0x18001fc81  cmp     [rdx+rcx*2], r9w
0x18001fc86  jnz     short loc_18001FC7E
0x18001fc88  lea     ecx, ds:2[rcx*2]
0x18001fc8f  jmp     short loc_18001FC97
0x18001fc91  mov     rdx, r10
0x18001fc94  mov     ecx, r11d
0x18001fc97  movzx   eax, byte ptr [r8]
0x18001fc9b  shl     eax, 18h
0x18001fc9e  mov     dword ptr [rsp+0E0h+EventDescriptor.Id], eax
0x18001fca2  movzx   eax, word ptr [r8+1]
0x18001fca7  mov     dword ptr [rbp+27h+EventDescriptor.Level], eax
0x18001fcaa  mov     rax, [r8+3]
0x18001fcae  mov     [rbp+27h+EventDescriptor.Keyword], rax
0x18001fcb2  mov     rax, cs:off_180053220
0x18001fcb9  mov     [rbp+27h+var_90.Ptr], rax
0x18001fcbd  mov     [rbp+27h+var_68], ecx
0x18001fcc0  lea     rcx, [r8+0Bh]
0x18001fcc4  mov     [rbp+27h+var_70], rdx
0x18001fcc8  xor     r8d, r8d; ActivityId
0x18001fccb  mov     [rbp+27h+var_64], r9d
0x18001fccf  lea     rdx, [rsp+0E0h+EventDescriptor]; EventDescriptor
0x18001fcd4  movzx   eax, word ptr [rax]
0x18001fcd7  mov     [rbp+27h+var_90.Size], eax
0x18001fcda  movzx   eax, word ptr [rcx]
0x18001fcdd  mov     [rbp+27h+var_78], eax
0x18001fce0  lea     rax, _TraceLoggingMetadataEnd
0x18001fce7  mov     [rbp+27h+var_80], rcx
0x18001fceb  lea     rcx, _TraceLoggingMetadata
0x18001fcf2  sub     eax, ecx
0x18001fcf4  mov     dword ptr [rbp+27h+var_90.0Ch], r11d
0x18001fcf8  mov     [rbp+27h+var_74], 1
0x18001fcff  mov     [rsp+0E0h+var_B0], eax
0x18001fd03  mov     eax, [rsp+0E0h+var_B0]
0x18001fd07  mov     rcx, cs:RegHandle; RegHandle
0x18001fd0e  lea     rax, [rbp+27h+var_90]
0x18001fd12  mov     [rsp+0E0h+UserData], rax; UserData
0x18001fd17  mov     [rsp+0E0h+UserDataCount], 8; UserDataCount
0x18001fd1f  call    cs:__imp_EventWriteTransfer
0x18001fd25  mov     rcx, [rbp+27h+var_10]
0x18001fd29  xor     rcx, rsp; StackCookie
0x18001fd2c  call    __security_check_cookie
0x18001fd31  add     rsp, 0E0h
0x18001fd38  pop     rbp
0x18001fd39  retn
```
