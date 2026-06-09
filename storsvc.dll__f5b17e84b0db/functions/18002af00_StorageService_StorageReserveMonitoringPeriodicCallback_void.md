# StorageService::StorageReserveMonitoringPeriodicCallback(void)

- ea: `0x18002af00`
- end: `0x18002b088`
- name: `?StorageReserveMonitoringPeriodicCallback@StorageService@@KAXXZ`
- size: `392`
- prototype: `void(void)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x180001148`
- `0x180002758`
- `0x18000d030`
- `0x18000ddb0`
- `0x18002af00`
- `0x1800375c0`
- `0x18006a970`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002afab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002afab`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002af69`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002af69`

## pseudocode

```c
void StorageService::StorageReserveMonitoringPeriodicCallback(void)
{
  unsigned int v0; // ebx
  __int64 (*v1)[12]; // r8
  int StorageReserve; // edi
  signed int LastError; // eax
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  int v7; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v8; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v9; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v10; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v11; // [rsp+68h] [rbp-98h] BYREF
  __int64 v12; // [rsp+70h] [rbp-90h] BYREF
  __int64 v13; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v14; // [rsp+80h] [rbp-80h] BYREF
  int v15; // [rsp+88h] [rbp-78h]
  unsigned __int16 v16[48]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Buffer[264]; // [rsp+F0h] [rbp-10h] BYREF

  memset_0(Buffer, 0, 0x208u);
  v9 = 0;
  v10 = 0;
  memset_0(v16, -1, sizeof(v16));
  if ( GetSystemDirectoryW(Buffer, 0x104u) )
  {
    Buffer[2] = 0;
    v0 = 0;
    SvcGetStorageDeviceSize(0, Buffer, 0, &v10, &v9);
    StorageReserve = StorageReserveHelper::QueryStorageReserveEx((StorageReserveHelper *)Buffer, v16, v1);
  }
  else
  {
    StorageReserve = 0;
    LastError = GetLastError();
    v0 = LastError;
    if ( LastError > 0 )
      v0 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( (unsigned int)dword_1800BF000 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_1800BF000, 0x400000000000LL) )
    {
      v15 = 96;
      v14 = v16;
      v11 = v9;
      v12 = v10;
      v7 = StorageReserve;
      v8 = v0;
      v13 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperPtrSize>(
        v4,
        (unsigned int)byte_1800A5985,
        v5,
        v6,
        (__int64)&v13,
        (__int64)&v8,
        (__int64)&v7,
        (__int64)&v12,
        (__int64)&v11,
        (__int64)&v14);
    }
  }
}

```

## disassembly

```asm
0x18002af00  mov     [rsp-8+arg_0], rbx
0x18002af05  mov     [rsp-8+arg_8], rdi
0x18002af0a  push    rbp
0x18002af0b  lea     rbp, [rsp-210h]
0x18002af13  sub     rsp, 310h
0x18002af1a  mov     rax, cs:__security_cookie
0x18002af21  xor     rax, rsp
0x18002af24  mov     [rbp+210h+var_10], rax
0x18002af2b  xor     edx, edx; Val
0x18002af2d  lea     rcx, [rbp+210h+Buffer]; void *
0x18002af31  mov     r8d, 208h; Size
0x18002af37  call    memset_0
0x18002af3c  mov     r8d, 60h ; '`'; Size
0x18002af42  mov     [rsp+310h+var_2B8], 0
0x18002af4b  or      edx, 0FFFFFFFFh; Val
0x18002af4e  mov     [rsp+310h+var_2B0], 0
0x18002af57  lea     rcx, [rbp+210h+var_280]; void *
0x18002af5b  call    memset_0
0x18002af60  mov     edx, 104h; uSize
0x18002af65  lea     rcx, [rbp+210h+Buffer]; lpBuffer
0x18002af69  call    cs:__imp_GetSystemDirectoryW
0x18002af6f  test    eax, eax
0x18002af71  jz      short loc_18002AFA9
0x18002af73  xor     eax, eax
0x18002af75  lea     r9, [rsp+310h+var_2B0]
0x18002af7a  mov     [rbp+210h+var_21C], ax
0x18002af7e  lea     rdx, [rbp+210h+Buffer]
0x18002af82  lea     rax, [rsp+310h+var_2B8]
0x18002af87  xor     r8d, r8d
0x18002af8a  xor     ecx, ecx
0x18002af8c  mov     [rsp+310h+var_2F0], rax
0x18002af91  xor     ebx, ebx
0x18002af93  call    SvcGetStorageDeviceSize
0x18002af98  lea     rdx, [rbp+210h+var_280]; unsigned __int16 *
0x18002af9c  lea     rcx, [rbp+210h+Buffer]; this
0x18002afa0  call    ?QueryStorageReserveEx@StorageReserveHelper@@YAJPEBGAEAY0M@_J@Z; StorageReserveHelper::QueryStorageReserveEx(ushort const *,__int64 (&)[12])
0x18002afa5  mov     edi, eax
0x18002afa7  jmp     short loc_18002AFC0
0x18002afa9  xor     edi, edi
0x18002afab  call    cs:__imp_GetLastError
0x18002afb1  mov     ebx, eax
0x18002afb3  test    eax, eax
0x18002afb5  jle     short loc_18002AFC0
0x18002afb7  movzx   ebx, ax
0x18002afba  or      ebx, 80070000h
0x18002afc0  mov     eax, cs:dword_1800BF000
0x18002afc6  cmp     eax, 5
0x18002afc9  jbe     loc_18002B064
0x18002afcf  mov     rdx, 400000000000h
0x18002afd9  lea     rcx, dword_1800BF000
0x18002afe0  call    _tlgKeywordOn
0x18002afe5  test    al, al
0x18002afe7  jz      short loc_18002B064
0x18002afe9  lea     rax, [rbp+210h+var_280]
0x18002afed  mov     [rbp+210h+var_288], 60h ; '`'
0x18002aff4  mov     [rbp+210h+var_290], rax
0x18002aff8  lea     rdx, byte_1800A5985
0x18002afff  mov     rax, [rsp+310h+var_2B8]
0x18002b004  mov     [rsp+310h+var_2A8], rax
0x18002b009  mov     rax, [rsp+310h+var_2B0]
0x18002b00e  mov     [rsp+310h+var_2A0], rax
0x18002b013  lea     rax, [rbp+210h+var_290]
0x18002b017  mov     [rsp+310h+var_2C8], rax
0x18002b01c  lea     rax, [rsp+310h+var_2A8]
0x18002b021  mov     [rsp+310h+var_2D0], rax
0x18002b026  lea     rax, [rsp+310h+var_2A0]
0x18002b02b  mov     [rsp+310h+var_2D8], rax
0x18002b030  lea     rax, [rsp+310h+var_2C0]
0x18002b035  mov     [rsp+310h+var_2E0], rax
0x18002b03a  lea     rax, [rsp+310h+var_2BC]
0x18002b03f  mov     [rsp+310h+var_2E8], rax
0x18002b044  lea     rax, [rsp+310h+var_298]
0x18002b049  mov     [rsp+310h+var_2F0], rax
0x18002b04e  mov     [rsp+310h+var_2C0], edi
0x18002b052  mov     [rsp+310h+var_2BC], ebx
0x18002b056  mov     [rsp+310h+var_298], 1000000h
0x18002b05f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U1@U1@U_tlgWrapperPtrSize@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@433AEBU_tlgWrapperPtrSize@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperPtrSize>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperPtrSize const &)
0x18002b064  mov     rcx, [rbp+210h+var_10]
0x18002b06b  xor     rcx, rsp; StackCookie
0x18002b06e  call    __security_check_cookie
0x18002b073  lea     r11, [rsp+310h+var_s0]
0x18002b07b  mov     rbx, [r11+10h]
0x18002b07f  mov     rdi, [r11+18h]
0x18002b083  mov     rsp, r11
0x18002b086  pop     rbp
0x18002b087  retn
```
