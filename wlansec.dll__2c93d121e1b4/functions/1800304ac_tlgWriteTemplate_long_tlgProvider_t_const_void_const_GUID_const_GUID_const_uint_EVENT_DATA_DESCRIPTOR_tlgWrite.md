# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x1800304ac`
- end: `0x18003067c`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U3@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@545@Z`
- size: `464`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18003f780`

## callees

- `0x1800304ac`
- `0x180043a30`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180030612`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180030612`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        const unsigned __int16 **a7,
        const unsigned __int16 **a8,
        __int64 a9,
        const unsigned __int16 **a10)
{
  __int64 v10; // rcx
  const unsigned __int16 *v12; // r8
  int v13; // eax
  const unsigned __int16 *v14; // rdx
  int v15; // eax
  const unsigned __int16 *v16; // rdx
  int v17; // eax
  const unsigned __int16 *v18; // rdx
  int v19; // ecx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-81h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int8 *v26; // [rsp+60h] [rbp-59h]
  int v27; // [rsp+68h] [rbp-51h]
  int v28; // [rsp+6Ch] [rbp-4Dh]
  const unsigned __int16 *v29; // [rsp+70h] [rbp-49h]
  int v30; // [rsp+78h] [rbp-41h]
  int v31; // [rsp+7Ch] [rbp-3Dh]
  __int64 v32; // [rsp+80h] [rbp-39h]
  __int64 v33; // [rsp+88h] [rbp-31h]
  const unsigned __int16 *v34; // [rsp+90h] [rbp-29h]
  int v35; // [rsp+98h] [rbp-21h]
  int v36; // [rsp+9Ch] [rbp-1Dh]
  const unsigned __int16 *v37; // [rsp+A0h] [rbp-19h]
  int v38; // [rsp+A8h] [rbp-11h]
  int v39; // [rsp+ACh] [rbp-Dh]
  __int64 v40; // [rsp+B0h] [rbp-9h]
  __int64 v41; // [rsp+B8h] [rbp-1h]
  const unsigned __int16 *v42; // [rsp+C0h] [rbp+7h]
  int v43; // [rsp+C8h] [rbp+Fh]
  int v44; // [rsp+CCh] [rbp+13h]

  v10 = -1;
  v12 = *a10;
  if ( *a10 )
  {
    v21 = -1;
    do
      ++v21;
    while ( *((_BYTE *)v12 + v21) );
    v13 = v21 + 1;
  }
  else
  {
    v12 = &qword_18009B258;
    v13 = 1;
  }
  v43 = v13;
  v40 = a9;
  v42 = v12;
  v44 = 0;
  v41 = 4;
  v14 = *a8;
  if ( *a8 )
  {
    v22 = -1;
    do
      ++v22;
    while ( *((_BYTE *)v14 + v22) );
    v15 = v22 + 1;
  }
  else
  {
    v14 = &qword_18009B258;
    v15 = 1;
  }
  v38 = v15;
  v37 = v14;
  v39 = 0;
  v16 = *a7;
  if ( *a7 )
  {
    v23 = -1;
    do
      ++v23;
    while ( *((_BYTE *)v16 + v23) );
    v17 = v23 + 1;
  }
  else
  {
    v16 = &qword_18009B258;
    v17 = 1;
  }
  v35 = v17;
  v32 = a6;
  v34 = v16;
  v36 = 0;
  v33 = 4;
  v18 = *a5;
  if ( *a5 )
  {
    do
      ++v10;
    while ( v18[v10] );
    v19 = 2 * v10 + 2;
  }
  else
  {
    v18 = &byte_18009AFB8;
    v19 = 2;
  }
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_1800AE350;
  v30 = v19;
  v29 = v18;
  v31 = 0;
  UserData.Size = *(unsigned __int16 *)off_1800AE350;
  v27 = *(unsigned __int16 *)(a2 + 11);
  v26 = a2 + 11;
  UserData.Reserved = 2;
  v28 = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 8u, &UserData);
}

```

## disassembly

```asm
0x1800304ac  push    rbp
0x1800304ae  lea     rbp, [rsp-27h]
0x1800304b3  sub     rsp, 0E0h
0x1800304ba  mov     rax, cs:__security_cookie
0x1800304c1  xor     rax, rsp
0x1800304c4  mov     [rbp+27h+var_10], rax
0x1800304c8  mov     rax, [rbp+27h+arg_48]
0x1800304cc  lea     r11, qword_18009B258
0x1800304d3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800304d7  xor     r10d, r10d
0x1800304da  mov     r9, rdx
0x1800304dd  mov     r8, [rax]
0x1800304e0  test    r8, r8
0x1800304e3  jnz     loc_180030634
0x1800304e9  mov     r8, r11
0x1800304ec  lea     eax, [rcx+2]
0x1800304ef  mov     [rbp+27h+var_18], eax
0x1800304f2  mov     rax, [rbp+27h+arg_40]
0x1800304f6  mov     [rbp+27h+var_30], rax
0x1800304fa  mov     rax, [rbp+27h+arg_38]
0x1800304fe  mov     [rbp+27h+var_20], r8
0x180030502  mov     [rbp+27h+var_14], r10d
0x180030506  mov     [rbp+27h+var_28], 4
0x18003050e  mov     rdx, [rax]
0x180030511  test    rdx, rdx
0x180030514  jnz     loc_180030647
0x18003051a  mov     rdx, r11
0x18003051d  mov     eax, 1
0x180030522  mov     [rbp+27h+var_38], eax
0x180030525  mov     rax, [rbp+27h+arg_30]
0x180030529  mov     [rbp+27h+var_40], rdx
0x18003052d  mov     [rbp+27h+var_34], r10d
0x180030531  mov     rdx, [rax]
0x180030534  test    rdx, rdx
0x180030537  jnz     loc_18003065A
0x18003053d  mov     rdx, r11
0x180030540  mov     eax, 1
0x180030545  mov     [rbp+27h+var_48], eax
0x180030548  mov     r8d, 2
0x18003054e  mov     rax, [rbp+27h+arg_28]
0x180030552  mov     [rbp+27h+var_60], rax
0x180030556  mov     rax, [rbp+27h+arg_20]
0x18003055a  mov     [rbp+27h+var_50], rdx
0x18003055e  mov     [rbp+27h+var_44], r10d
0x180030562  mov     [rbp+27h+var_58], 4
0x18003056a  mov     rdx, [rax]
0x18003056d  test    rdx, rdx
0x180030570  jz      loc_18003066D
0x180030576  inc     rcx
0x180030579  cmp     [rdx+rcx*2], r10w
0x18003057e  jnz     short loc_180030576
0x180030580  lea     ecx, ds:2[rcx*2]
0x180030587  movzx   eax, byte ptr [r9]
0x18003058b  shl     eax, 18h
0x18003058e  mov     dword ptr [rsp+0E0h+EventDescriptor.Id], eax
0x180030592  movzx   eax, word ptr [r9+1]
0x180030597  mov     dword ptr [rbp+27h+EventDescriptor.Level], eax
0x18003059a  mov     rax, [r9+3]
0x18003059e  mov     [rbp+27h+EventDescriptor.Keyword], rax
0x1800305a2  mov     rax, cs:off_1800AE350
0x1800305a9  mov     [rbp+27h+var_90.Ptr], rax
0x1800305ad  mov     [rbp+27h+var_68], ecx
0x1800305b0  lea     rcx, [r9+0Bh]
0x1800305b4  mov     [rbp+27h+var_70], rdx
0x1800305b8  xor     r9d, r9d; RelatedActivityId
0x1800305bb  mov     [rbp+27h+var_64], r10d
0x1800305bf  lea     rdx, [rsp+0E0h+EventDescriptor]; EventDescriptor
0x1800305c4  movzx   eax, word ptr [rax]
0x1800305c7  mov     [rbp+27h+var_90.Size], eax
0x1800305ca  movzx   eax, word ptr [rcx]
0x1800305cd  mov     [rbp+27h+var_78], eax
0x1800305d0  lea     rax, _TraceLoggingMetadataEnd
0x1800305d7  mov     [rbp+27h+var_80], rcx
0x1800305db  lea     rcx, _TraceLoggingMetadata
0x1800305e2  sub     eax, ecx
0x1800305e4  mov     dword ptr [rbp+27h+var_90.0Ch], r8d
0x1800305e8  mov     [rbp+27h+var_74], 1
0x1800305ef  xor     r8d, r8d; ActivityId
0x1800305f2  mov     [rsp+0E0h+var_B0], eax
0x1800305f6  mov     eax, [rsp+0E0h+var_B0]
0x1800305fa  mov     rcx, cs:RegHandle; RegHandle
0x180030601  lea     rax, [rbp+27h+var_90]
0x180030605  mov     [rsp+0E0h+UserData], rax; UserData
0x18003060a  mov     [rsp+0E0h+UserDataCount], 8; UserDataCount
0x180030612  call    cs:__imp_EventWriteTransfer
0x180030619  nop     dword ptr [rax+rax+00h]
0x18003061e  mov     rcx, [rbp+27h+var_10]
0x180030622  xor     rcx, rsp; StackCookie
0x180030625  call    __security_check_cookie
0x18003062a  add     rsp, 0E0h
0x180030631  pop     rbp
0x180030632  retn
0x180030634  mov     rax, rcx
0x180030637  inc     rax
0x18003063a  cmp     [r8+rax], r10b
0x18003063e  jnz     short loc_180030637
0x180030640  inc     eax
0x180030642  jmp     loc_1800304EF
0x180030647  mov     rax, rcx
0x18003064a  inc     rax
0x18003064d  cmp     [rdx+rax], r10b
0x180030651  jnz     short loc_18003064A
0x180030653  inc     eax
0x180030655  jmp     loc_180030522
0x18003065a  mov     rax, rcx
0x18003065d  inc     rax
0x180030660  cmp     [rdx+rax], r10b
0x180030664  jnz     short loc_18003065D
0x180030666  inc     eax
0x180030668  jmp     loc_180030545
0x18003066d  lea     rdx, byte_18009AFB8
0x180030674  mov     ecx, r8d
0x180030677  jmp     loc_180030587
```
