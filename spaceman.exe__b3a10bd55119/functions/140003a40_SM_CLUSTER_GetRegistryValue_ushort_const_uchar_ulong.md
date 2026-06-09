# SM_CLUSTER::GetRegistryValue(ushort const *,uchar *,ulong *)

- ea: `0x140003a40`
- end: `0x140003b4d`
- name: `?GetRegistryValue@SM_CLUSTER@@QEAAHPEBGPEAEPEAK@Z`
- size: `269`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400032b0`

## callees

- `0x140001008`
- `0x1400010b0`
- `0x140003a40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003ab7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003ab7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003abd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003abd`
- `ext-ms-win-cluster-clusapi-l1-1-1!ClusterRegQueryValue` at `0x140003aa9`
- `ext-ms-win-cluster-clusapi-l1-1-1!ClusterRegQueryValue` at `0x140003aa9`

## string_xrefs

- `0x140003a56`: `SM_CLUSTER::GetRegistryValue`

## pseudocode

```c
__int64 __fastcall SM_CLUSTER::GetRegistryValue(
        HKEY *this,
        const unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  LONG Value; // eax
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
    v19 = 168;
    v17 = "SM_CLUSTER::GetRegistryValue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)this,
      (unsigned int)qword_140010B00,
      (_DWORD)a3,
      (_DWORD)a4,
      (__int64)&v17,
      (__int64)&v19);
  }
  Value = ClusterRegQueryValue(this[2], a2, 0, a3, a4);
  if ( Value )
  {
    v12 = 0;
    SetLastError(Value);
    LastError = GetLastError();
    if ( (unsigned int)dword_140014048 > 2 )
    {
      v19 = LastError;
      LODWORD(v17) = 191;
      v18[0] = "SM_CLUSTER::GetRegistryValue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        dword_140014048,
        (unsigned int)byte_140010C19,
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
      v19 = 191;
      v18[0] = "SM_CLUSTER::GetRegistryValue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned int)byte_140010C4D,
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
0x140003a40  push    rbp
0x140003a42  push    rbx
0x140003a43  push    rsi
0x140003a44  push    rdi
0x140003a45  push    r14
0x140003a47  push    r15
0x140003a49  mov     rbp, rsp
0x140003a4c  sub     rsp, 58h
0x140003a50  mov     eax, cs:dword_140014048
0x140003a56  lea     r15, aSmClusterGetre; "SM_CLUSTER::GetRegistryValue"
0x140003a5d  mov     rbx, r9
0x140003a60  mov     rdi, r8
0x140003a63  mov     rsi, rdx
0x140003a66  mov     r14, rcx
0x140003a69  cmp     eax, 5
0x140003a6c  jbe     short loc_140003A97
0x140003a6e  lea     rax, [rbp+arg_0]
0x140003a72  mov     [rbp+arg_0], 0A8h
0x140003a79  mov     [rsp+58h+var_30], rax
0x140003a7e  lea     rdx, qword_140010B00
0x140003a85  lea     rax, [rbp+var_18]
0x140003a89  mov     [rbp+var_18], r15
0x140003a8d  mov     [rsp+58h+lpcbData], rax
0x140003a92  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140003a97  mov     rcx, [r14+10h]; hKey
0x140003a9b  mov     r9, rdi; lpData
0x140003a9e  xor     r8d, r8d; lpdwValueType
0x140003aa1  mov     [rsp+58h+lpcbData], rbx; lpcbData
0x140003aa6  mov     rdx, rsi; lpszValueName
0x140003aa9  call    cs:__imp_ClusterRegQueryValue
0x140003aaf  test    eax, eax
0x140003ab1  jz      short loc_140003B05
0x140003ab3  mov     ecx, eax; dwErrCode
0x140003ab5  xor     ebx, ebx
0x140003ab7  call    cs:__imp_SetLastError
0x140003abd  call    cs:__imp_GetLastError
0x140003ac3  mov     ecx, cs:dword_140014048
0x140003ac9  cmp     ecx, 2
0x140003acc  jbe     short loc_140003B3E
0x140003ace  mov     [rbp+arg_0], eax
0x140003ad1  lea     rdx, byte_140010C19
0x140003ad8  lea     rax, [rbp+arg_0]
0x140003adc  mov     dword ptr [rbp+var_18], 0BFh
0x140003ae3  mov     [rsp+58h+var_28], rax
0x140003ae8  lea     rax, [rbp+var_18]
0x140003aec  mov     [rsp+58h+var_30], rax
0x140003af1  lea     rax, [rbp+var_10]
0x140003af5  mov     [rsp+58h+lpcbData], rax
0x140003afa  mov     [rbp+var_10], r15
0x140003afe  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140003b03  jmp     short loc_140003B3E
0x140003b05  mov     ebx, 1
0x140003b0a  mov     eax, cs:dword_140014048
0x140003b10  cmp     eax, 5
0x140003b13  jbe     short loc_140003B3E
0x140003b15  lea     rax, [rbp+arg_0]
0x140003b19  mov     [rbp+arg_0], 0BFh
0x140003b20  mov     [rsp+58h+var_30], rax
0x140003b25  lea     rdx, byte_140010C4D
0x140003b2c  lea     rax, [rbp+var_10]
0x140003b30  mov     [rbp+var_10], r15
0x140003b34  mov     [rsp+58h+lpcbData], rax
0x140003b39  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140003b3e  mov     eax, ebx
0x140003b40  add     rsp, 58h
0x140003b44  pop     r15
0x140003b46  pop     r14
0x140003b48  pop     rdi
0x140003b49  pop     rsi
0x140003b4a  pop     rbx
0x140003b4b  pop     rbp
0x140003b4c  retn
```
