# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18001f82c`
- end: `0x18001f976`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `330`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, __int64 **, __int64 **, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180023e18`

## callees

- `0x18001f82c`
- `0x18003fc30`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001f93d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001f93d`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5,
        __int64 **a6,
        __int64 a7)
{
  __int64 v7; // rcx
  __int64 *v9; // r8
  __int64 v10; // rax
  int v11; // eax
  __int64 *v12; // rdx
  int v13; // ecx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-21h] BYREF
  unsigned __int8 *v17; // [rsp+60h] [rbp-11h]
  int v18; // [rsp+68h] [rbp-9h]
  int v19; // [rsp+6Ch] [rbp-5h]
  __int64 *v20; // [rsp+70h] [rbp-1h]
  int v21; // [rsp+78h] [rbp+7h]
  int v22; // [rsp+7Ch] [rbp+Bh]
  __int64 *v23; // [rsp+80h] [rbp+Fh]
  int v24; // [rsp+88h] [rbp+17h]
  int v25; // [rsp+8Ch] [rbp+1Bh]
  __int64 v26; // [rsp+90h] [rbp+1Fh]
  __int64 v27; // [rsp+98h] [rbp+27h]

  v26 = a7;
  v7 = -1;
  v27 = 4;
  v9 = *a6;
  if ( *a6 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *((_WORD *)v9 + v10) );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v9 = &qword_180045B70;
    v11 = 2;
  }
  v24 = v11;
  v23 = v9;
  v25 = 0;
  v12 = *a5;
  if ( *a5 )
  {
    do
      ++v7;
    while ( *((_WORD *)v12 + v7) );
    v13 = 2 * v7 + 2;
  }
  else
  {
    v12 = &qword_180045B70;
    v13 = 2;
  }
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180053220;
  v21 = v13;
  v20 = v12;
  v22 = 0;
  UserData.Size = *(unsigned __int16 *)off_180053220;
  v18 = *(unsigned __int16 *)(a2 + 11);
  v17 = a2 + 11;
  UserData.Reserved = 2;
  v19 = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
}

```

## disassembly

```asm
0x18001f82c  push    rbp
0x18001f82e  lea     rbp, [rsp-3Fh]
0x18001f833  sub     rsp, 0B0h
0x18001f83a  mov     rax, cs:__security_cookie
0x18001f841  xor     rax, rsp
0x18001f844  mov     [rbp+3Fh+var_10], rax
0x18001f848  mov     rax, [rbp+3Fh+arg_30]
0x18001f84c  xor     r10d, r10d
0x18001f84f  mov     [rbp+3Fh+var_20], rax
0x18001f853  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001f857  mov     rax, [rbp+3Fh+arg_28]
0x18001f85b  mov     r9, rdx
0x18001f85e  mov     [rbp+3Fh+var_18], 4
0x18001f866  lea     r11d, [r10+2]
0x18001f86a  mov     r8, [rax]
0x18001f86d  test    r8, r8
0x18001f870  jz      loc_18001F958
0x18001f876  mov     rax, rcx
0x18001f879  inc     rax
0x18001f87c  cmp     [r8+rax*2], r10w
0x18001f881  jnz     short loc_18001F879
0x18001f883  lea     eax, ds:2[rax*2]
0x18001f88a  mov     [rbp+3Fh+var_28], eax
0x18001f88d  mov     rax, [rbp+3Fh+arg_20]
0x18001f891  mov     [rbp+3Fh+var_30], r8
0x18001f895  mov     [rbp+3Fh+var_24], r10d
0x18001f899  mov     rdx, [rax]
0x18001f89c  test    rdx, rdx
0x18001f89f  jz      loc_18001F967
0x18001f8a5  inc     rcx
0x18001f8a8  cmp     [rdx+rcx*2], r10w
0x18001f8ad  jnz     short loc_18001F8A5
0x18001f8af  lea     ecx, ds:2[rcx*2]
0x18001f8b6  movzx   eax, byte ptr [r9]
0x18001f8ba  xor     r8d, r8d; ActivityId
0x18001f8bd  shl     eax, 18h
0x18001f8c0  mov     dword ptr [rbp+3Fh+EventDescriptor.Id], eax
0x18001f8c3  movzx   eax, word ptr [r9+1]
0x18001f8c8  mov     dword ptr [rbp+3Fh+EventDescriptor.Level], eax
0x18001f8cb  mov     rax, [r9+3]
0x18001f8cf  mov     [rbp+3Fh+EventDescriptor.Keyword], rax
0x18001f8d3  mov     rax, cs:off_180053220
0x18001f8da  mov     [rbp+3Fh+var_60.Ptr], rax
0x18001f8de  mov     [rbp+3Fh+var_38], ecx
0x18001f8e1  lea     rcx, [r9+0Bh]
0x18001f8e5  mov     [rbp+3Fh+var_40], rdx
0x18001f8e9  xor     r9d, r9d; RelatedActivityId
0x18001f8ec  mov     [rbp+3Fh+var_34], r10d
0x18001f8f0  lea     rdx, [rbp+3Fh+EventDescriptor]; EventDescriptor
0x18001f8f4  movzx   eax, word ptr [rax]
0x18001f8f7  mov     [rbp+3Fh+var_60.Size], eax
0x18001f8fa  movzx   eax, word ptr [rcx]
0x18001f8fd  mov     [rbp+3Fh+var_48], eax
0x18001f900  lea     rax, _TraceLoggingMetadataEnd
0x18001f907  mov     [rbp+3Fh+var_50], rcx
0x18001f90b  lea     rcx, _TraceLoggingMetadata
0x18001f912  sub     eax, ecx
0x18001f914  mov     dword ptr [rbp+3Fh+var_60.0Ch], r11d
0x18001f918  mov     [rbp+3Fh+var_44], 1
0x18001f91f  mov     [rbp+3Fh+var_80], eax
0x18001f922  mov     eax, [rbp+3Fh+var_80]
0x18001f925  mov     rcx, cs:RegHandle; RegHandle
0x18001f92c  lea     rax, [rbp+3Fh+var_60]
0x18001f930  mov     [rsp+0B0h+UserData], rax; UserData
0x18001f935  mov     [rsp+0B0h+UserDataCount], 5; UserDataCount
0x18001f93d  call    cs:__imp_EventWriteTransfer
0x18001f943  mov     rcx, [rbp+3Fh+var_10]
0x18001f947  xor     rcx, rsp; StackCookie
0x18001f94a  call    __security_check_cookie
0x18001f94f  add     rsp, 0B0h
0x18001f956  pop     rbp
0x18001f957  retn
0x18001f958  lea     r8, qword_180045B70
0x18001f95f  mov     eax, r11d
0x18001f962  jmp     loc_18001F88A
0x18001f967  lea     rdx, qword_180045B70
0x18001f96e  mov     ecx, r11d
0x18001f971  jmp     loc_18001F8B6
```
