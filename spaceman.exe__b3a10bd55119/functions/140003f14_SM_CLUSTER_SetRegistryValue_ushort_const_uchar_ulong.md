# SM_CLUSTER::SetRegistryValue(ushort const *,uchar *,ulong)

- ea: `0x140003f14`
- end: `0x140004023`
- name: `?SetRegistryValue@SM_CLUSTER@@QEAAHPEBGPEAEK@Z`
- size: `271`
- prototype: `__int64 __fastcall(SM_CLUSTER *this, const unsigned __int16 *, unsigned __int8 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400032b0`

## callees

- `0x140001008`
- `0x1400010b0`
- `0x140003f14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003f8d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003f8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003f93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003f93`
- `ext-ms-win-cluster-clusapi-l1-1-1!ClusterRegSetValueForceSync` at `0x140003f7f`
- `ext-ms-win-cluster-clusapi-l1-1-1!ClusterRegSetValueForceSync` at `0x140003f7f`

## string_xrefs

- `0x140003f2a`: `SM_CLUSTER::SetRegistryValue`

## pseudocode

```c
__int64 __fastcall SM_CLUSTER::SetRegistryValue(
        SM_CLUSTER *this,
        const unsigned __int16 *a2,
        unsigned __int8 *a3,
        int a4)
{
  DWORD v8; // eax
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  unsigned int v12; // ebx
  DWORD LastError; // eax
  int v14; // r8d
  int v15; // r9d
  const char *v17; // [rsp+40h] [rbp-18h] BYREF
  _QWORD v18[2]; // [rsp+48h] [rbp-10h] BYREF
  int v19; // [rsp+90h] [rbp+38h] BYREF

  if ( (unsigned int)dword_140014048 > 5 )
  {
    v19 = 204;
    v17 = "SM_CLUSTER::SetRegistryValue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)this,
      (unsigned int)byte_140010F71,
      (_DWORD)a3,
      a4,
      (__int64)&v17,
      (__int64)&v19);
  }
  v8 = ClusterRegSetValueForceSync(*((_QWORD *)this + 2), a2, 3, a3, a4);
  if ( v8 )
  {
    v12 = 0;
    SetLastError(v8);
    LastError = GetLastError();
    if ( (unsigned int)dword_140014048 > 2 )
    {
      v19 = LastError;
      LODWORD(v17) = 225;
      v18[0] = "SM_CLUSTER::SetRegistryValue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        dword_140014048,
        (unsigned int)&word_140010B2E,
        v14,
        v15,
        (__int64)v18,
        (__int64)&v17,
        (__int64)&v19);
    }
  }
  else
  {
    v12 = 1;
    if ( (unsigned int)dword_140014048 > 5 )
    {
      v19 = 225;
      v18[0] = "SM_CLUSTER::SetRegistryValue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned int)&dword_140010CDC,
        v10,
        v11,
        (__int64)v18,
        (__int64)&v19);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x140003f14  push    rbp
0x140003f16  push    rbx
0x140003f17  push    rsi
0x140003f18  push    rdi
0x140003f19  push    r14
0x140003f1b  push    r15
0x140003f1d  mov     rbp, rsp
0x140003f20  sub     rsp, 58h
0x140003f24  mov     eax, cs:dword_140014048
0x140003f2a  lea     r15, aSmClusterSetre; "SM_CLUSTER::SetRegistryValue"
0x140003f31  mov     ebx, r9d
0x140003f34  mov     rdi, r8
0x140003f37  mov     rsi, rdx
0x140003f3a  mov     r14, rcx
0x140003f3d  cmp     eax, 5
0x140003f40  jbe     short loc_140003F6B
0x140003f42  lea     rax, [rbp+arg_0]
0x140003f46  mov     [rbp+arg_0], 0CCh
0x140003f4d  mov     [rsp+58h+var_30], rax
0x140003f52  lea     rdx, byte_140010F71
0x140003f59  lea     rax, [rbp+var_18]
0x140003f5d  mov     [rbp+var_18], r15
0x140003f61  mov     [rsp+58h+var_38], rax
0x140003f66  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140003f6b  mov     rcx, [r14+10h]
0x140003f6f  mov     r9, rdi
0x140003f72  mov     r8d, 3
0x140003f78  mov     dword ptr [rsp+58h+var_38], ebx
0x140003f7c  mov     rdx, rsi
0x140003f7f  call    cs:__imp_ClusterRegSetValueForceSync
0x140003f85  test    eax, eax
0x140003f87  jz      short loc_140003FDB
0x140003f89  mov     ecx, eax; dwErrCode
0x140003f8b  xor     ebx, ebx
0x140003f8d  call    cs:__imp_SetLastError
0x140003f93  call    cs:__imp_GetLastError
0x140003f99  mov     ecx, cs:dword_140014048
0x140003f9f  cmp     ecx, 2
0x140003fa2  jbe     short loc_140004014
0x140003fa4  mov     [rbp+arg_0], eax
0x140003fa7  lea     rdx, word_140010B2E
0x140003fae  lea     rax, [rbp+arg_0]
0x140003fb2  mov     dword ptr [rbp+var_18], 0E1h
0x140003fb9  mov     [rsp+58h+var_28], rax
0x140003fbe  lea     rax, [rbp+var_18]
0x140003fc2  mov     [rsp+58h+var_30], rax
0x140003fc7  lea     rax, [rbp+var_10]
0x140003fcb  mov     [rsp+58h+var_38], rax
0x140003fd0  mov     [rbp+var_10], r15
0x140003fd4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140003fd9  jmp     short loc_140004014
0x140003fdb  mov     ebx, 1
0x140003fe0  mov     eax, cs:dword_140014048
0x140003fe6  cmp     eax, 5
0x140003fe9  jbe     short loc_140004014
0x140003feb  lea     rax, [rbp+arg_0]
0x140003fef  mov     [rbp+arg_0], 0E1h
0x140003ff6  mov     [rsp+58h+var_30], rax
0x140003ffb  lea     rdx, dword_140010CDC
0x140004002  lea     rax, [rbp+var_10]
0x140004006  mov     [rbp+var_10], r15
0x14000400a  mov     [rsp+58h+var_38], rax
0x14000400f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140004014  mov     eax, ebx
0x140004016  add     rsp, 58h
0x14000401a  pop     r15
0x14000401c  pop     r14
0x14000401e  pop     rdi
0x14000401f  pop     rsi
0x140004020  pop     rbx
0x140004021  pop     rbp
0x140004022  retn
```
