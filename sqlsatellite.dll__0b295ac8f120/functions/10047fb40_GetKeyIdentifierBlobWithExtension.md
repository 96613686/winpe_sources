# GetKeyIdentifierBlobWithExtension

- ea: `0x10047fb40`
- end: `0x10047fd74`
- name: `GetKeyIdentifierBlobWithExtension`
- size: `564`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x10047fd80`

## callees

- `0x100455f90`
- `0x100478330`
- `0x10047fb40`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x10047fbcc`
- `KERNEL32!GetCurrentThreadId` at `0x10047fcda`
- `KERNEL32!GetCurrentThreadId` at `0x10047fbcc`
- `KERNEL32!GetCurrentThreadId` at `0x10047fcda`
- `KERNEL32!GetLastError` at `0x10047fbae`
- `KERNEL32!GetLastError` at `0x10047fcbc`
- `KERNEL32!GetLastError` at `0x10047fbae`
- `KERNEL32!GetLastError` at `0x10047fcbc`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x10047fc3d`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x10047fd4b`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x10047fc3d`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x10047fd4b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10047fc72`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10047fc72`
- `CRYPT32!CryptDecodeObject` at `0x10047fb99`
- `CRYPT32!CryptDecodeObject` at `0x10047fcae`
- `CRYPT32!CryptDecodeObject` at `0x10047fb99`
- `CRYPT32!CryptDecodeObject` at `0x10047fcae`

## string_xrefs

- `0x10047fb9f`: `GetKeyIdentifierBlobWithExtension`
- `0x10047fc43`: `GetKeyIdentifierBlobWithExtension`
- `0x10047fc55`: `Sql\Ntdbms\extensibility\common\src\ExtensibilityCertCreator.cpp`

## pseudocode

```c
__int64 __fastcall GetKeyIdentifierBlobWithExtension(__int64 a1, struct IMemObj *a2, __int64 a3, DWORD *pcbStructInfo)
{
  signed int v8; // ebx
  signed int LastError; // eax
  DWORD CurrentThreadId; // eax
  __int64 v11; // rdi
  void *pvStructInfo; // rax
  signed int v14; // eax
  DWORD v15; // eax
  __int64 v16; // rdi
  __int128 v17; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+50h] [rbp-B0h]
  signed int v19; // [rsp+58h] [rbp-A8h]
  DWORD v20; // [rsp+5Ch] [rbp-A4h]
  const char *v21; // [rsp+60h] [rbp-A0h]
  int v22; // [rsp+68h] [rbp-98h]
  _BYTE v23[216]; // [rsp+70h] [rbp-90h] BYREF
  int v24; // [rsp+148h] [rbp+48h]
  __int64 v25; // [rsp+150h] [rbp+50h]

  v8 = 0;
  if ( CryptDecodeObject(0x10001u, "2.5.29.14", *(const BYTE **)(a1 + 24), *(_DWORD *)(a1 + 16), 0, 0, pcbStructInfo) )
    goto LABEL_11;
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError > 0 )
    v8 = (unsigned __int16)LastError | 0x80070000;
  if ( g_extensibilityErrorRingBuffer )
  {
    CurrentThreadId = GetCurrentThreadId();
    v21 = "GetKeyIdentifierBlobWithExtension";
    v11 = g_extensibilityErrorRingBuffer;
    v17 = 0;
    v18 = 0;
    v19 = v8;
    v20 = CurrentThreadId;
    v22 = 313;
    v24 = 0;
    v25 = 0;
    if ( *(_QWORD *)(g_extensibilityErrorRingBuffer + 64LL) )
      StackFrames<24>::CaptureCurrent(v23, 1);
    if ( (dword_1005113AC & 0x10) != 0 )
      ExtensibilityErrorRecord::FireMatchingEvent(&v17, v23);
    SOS_RingBuffer::StoreRecordInternalWithoutEvent(v11, &v17, v23);
  }
  if ( v8 >= 0 )
  {
LABEL_11:
    pvStructInfo = operator new[](
                     *pcbStructInfo,
                     a2,
                     1,
                     "Sql\\Ntdbms\\extensibility\\common\\src\\ExtensibilityCertCreator.cpp",
                     320,
                     6u);
    *(_QWORD *)(a3 + 16) = pvStructInfo;
    if ( !pvStructInfo )
      return 2147942414LL;
    if ( !CryptDecodeObject(
            0x10001u,
            "2.5.29.14",
            *(const BYTE **)(a1 + 24),
            *(_DWORD *)(a1 + 16),
            0,
            pvStructInfo,
            pcbStructInfo) )
    {
      v14 = GetLastError();
      v8 = v14;
      if ( v14 > 0 )
        v8 = (unsigned __int16)v14 | 0x80070000;
      if ( g_extensibilityErrorRingBuffer )
      {
        v15 = GetCurrentThreadId();
        v21 = "GetKeyIdentifierBlobWithExtension";
        v16 = g_extensibilityErrorRingBuffer;
        v17 = 0;
        v18 = 0;
        v19 = v8;
        v20 = v15;
        v22 = 341;
        v24 = 0;
        v25 = 0;
        if ( *(_QWORD *)(g_extensibilityErrorRingBuffer + 64LL) )
          StackFrames<24>::CaptureCurrent(v23, 1);
        if ( (dword_1005113AC & 0x10) != 0 )
          ExtensibilityErrorRecord::FireMatchingEvent(&v17, v23);
        SOS_RingBuffer::StoreRecordInternalWithoutEvent(v16, &v17, v23);
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x10047fb40  mov     [rsp-8+arg_0], rbx
0x10047fb45  mov     [rsp-8+arg_8], rsi
0x10047fb4a  mov     [rsp-8+arg_10], rdi
0x10047fb4f  push    rbp
0x10047fb50  push    r12
0x10047fb52  push    r13
0x10047fb54  push    r14
0x10047fb56  push    r15
0x10047fb58  lea     rbp, [rsp-60h]
0x10047fb5d  sub     rsp, 160h
0x10047fb64  mov     [rsp+180h+pcbStructInfo], r9; pcbStructInfo
0x10047fb69  xor     r13d, r13d
0x10047fb6c  mov     r14, r9
0x10047fb6f  mov     [rsp+180h+pvStructInfo], r13; pvStructInfo
0x10047fb74  mov     r9d, [rcx+10h]; cbEncoded
0x10047fb78  mov     r15, r8
0x10047fb7b  mov     r8, [rcx+18h]; pbEncoded
0x10047fb7f  mov     r12, rdx
0x10047fb82  mov     rsi, rcx
0x10047fb85  mov     [rsp+180h+dwFlags], r13d; dwFlags
0x10047fb8a  mov     ecx, 10001h; dwCertEncodingType
0x10047fb8f  lea     rdx, pszObjId; "2.5.29.14"
0x10047fb96  mov     ebx, r13d
0x10047fb99  call    cs:__imp_CryptDecodeObject
0x10047fb9f  lea     rdi, aGetkeyidentifi; "GetKeyIdentifierBlobWithExtension"
0x10047fba6  test    eax, eax
0x10047fba8  jnz     loc_10047FC52
0x10047fbae  call    cs:__imp_GetLastError
0x10047fbb4  mov     ebx, eax
0x10047fbb6  test    eax, eax
0x10047fbb8  jle     short loc_10047FBC3
0x10047fbba  movzx   ebx, ax
0x10047fbbd  or      ebx, 80070000h
0x10047fbc3  cmp     cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A, r13; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x10047fbca  jz      short loc_10047FC4A
0x10047fbcc  call    cs:__imp_GetCurrentThreadId
0x10047fbd2  mov     [rsp+180h+var_120], rdi
0x10047fbd7  xor     ecx, ecx
0x10047fbd9  mov     rdi, cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x10047fbe0  xorps   xmm0, xmm0
0x10047fbe3  movups  [rsp+180h+var_140], xmm0
0x10047fbe8  mov     [rsp+180h+var_130], rcx
0x10047fbed  mov     [rsp+180h+var_128], ebx
0x10047fbf1  mov     [rsp+180h+var_124], eax
0x10047fbf5  mov     [rsp+180h+var_118], 139h
0x10047fbfd  mov     [rbp+80h+var_38], r13d
0x10047fc01  mov     [rbp+80h+var_30], r13
0x10047fc05  cmp     [rdi+40h], rcx
0x10047fc09  jz      short loc_10047FC18
0x10047fc0b  lea     edx, [rcx+1]
0x10047fc0e  lea     rcx, [rsp+180h+var_110]
0x10047fc13  call    ?CaptureCurrent@?$StackFrames@$0BI@@@QEAAXI@Z; StackFrames<24>::CaptureCurrent(uint)
0x10047fc18  test    byte ptr cs:dword_1005113AC, 10h
0x10047fc1f  jz      short loc_10047FC30
0x10047fc21  lea     rdx, [rsp+180h+var_110]
0x10047fc26  lea     rcx, [rsp+180h+var_140]
0x10047fc2b  call    ?FireMatchingEvent@ExtensibilityErrorRecord@@QEAAXPEAV?$StackFrames@$0BI@@@@Z; ExtensibilityErrorRecord::FireMatchingEvent(StackFrames<24> *)
0x10047fc30  lea     r8, [rsp+180h+var_110]
0x10047fc35  mov     rcx, rdi
0x10047fc38  lea     rdx, [rsp+180h+var_140]
0x10047fc3d  call    cs:__imp_?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z; SOS_RingBuffer::StoreRecordInternalWithoutEvent(SOS_RingBufferRecord *,StackFrames<24> *)
0x10047fc43  lea     rdi, aGetkeyidentifi; "GetKeyIdentifierBlobWithExtension"
0x10047fc4a  test    ebx, ebx
0x10047fc4c  js      loc_10047FD51
0x10047fc52  mov     ecx, [r14]
0x10047fc55  lea     r9, aSqlNtdbmsExten_6; "Sql\\Ntdbms\\extensibility\\common\\src"...
0x10047fc5c  mov     byte ptr [rsp+180h+pvStructInfo], 6
0x10047fc61  mov     r8d, 1
0x10047fc67  mov     rdx, r12
0x10047fc6a  mov     [rsp+180h+dwFlags], 140h
0x10047fc72  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10047fc78  mov     [r15+10h], rax
0x10047fc7c  test    rax, rax
0x10047fc7f  jnz     short loc_10047FC8B
0x10047fc81  mov     eax, 8007000Eh
0x10047fc86  jmp     loc_10047FD53
0x10047fc8b  mov     r9d, [rsi+10h]; cbEncoded
0x10047fc8f  lea     rdx, pszObjId; "2.5.29.14"
0x10047fc96  mov     r8, [rsi+18h]; pbEncoded
0x10047fc9a  mov     ecx, 10001h; dwCertEncodingType
0x10047fc9f  mov     [rsp+180h+pcbStructInfo], r14; pcbStructInfo
0x10047fca4  mov     [rsp+180h+pvStructInfo], rax; pvStructInfo
0x10047fca9  mov     [rsp+180h+dwFlags], r13d; dwFlags
0x10047fcae  call    cs:__imp_CryptDecodeObject
0x10047fcb4  test    eax, eax
0x10047fcb6  jnz     loc_10047FD51
0x10047fcbc  call    cs:__imp_GetLastError
0x10047fcc2  mov     ebx, eax
0x10047fcc4  test    eax, eax
0x10047fcc6  jle     short loc_10047FCD1
0x10047fcc8  movzx   ebx, ax
0x10047fccb  or      ebx, 80070000h
0x10047fcd1  cmp     cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A, r13; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x10047fcd8  jz      short loc_10047FD51
0x10047fcda  call    cs:__imp_GetCurrentThreadId
0x10047fce0  mov     [rsp+180h+var_120], rdi
0x10047fce5  xor     ecx, ecx
0x10047fce7  mov     rdi, cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x10047fcee  xorps   xmm0, xmm0
0x10047fcf1  movups  [rsp+180h+var_140], xmm0
0x10047fcf6  mov     [rsp+180h+var_130], rcx
0x10047fcfb  mov     [rsp+180h+var_128], ebx
0x10047fcff  mov     [rsp+180h+var_124], eax
0x10047fd03  mov     [rsp+180h+var_118], 155h
0x10047fd0b  mov     [rbp+80h+var_38], r13d
0x10047fd0f  mov     [rbp+80h+var_30], r13
0x10047fd13  cmp     [rdi+40h], rcx
0x10047fd17  jz      short loc_10047FD26
0x10047fd19  lea     edx, [rcx+1]
0x10047fd1c  lea     rcx, [rsp+180h+var_110]
0x10047fd21  call    ?CaptureCurrent@?$StackFrames@$0BI@@@QEAAXI@Z; StackFrames<24>::CaptureCurrent(uint)
0x10047fd26  test    byte ptr cs:dword_1005113AC, 10h
0x10047fd2d  jz      short loc_10047FD3E
0x10047fd2f  lea     rdx, [rsp+180h+var_110]
0x10047fd34  lea     rcx, [rsp+180h+var_140]
0x10047fd39  call    ?FireMatchingEvent@ExtensibilityErrorRecord@@QEAAXPEAV?$StackFrames@$0BI@@@@Z; ExtensibilityErrorRecord::FireMatchingEvent(StackFrames<24> *)
0x10047fd3e  lea     r8, [rsp+180h+var_110]
0x10047fd43  mov     rcx, rdi
0x10047fd46  lea     rdx, [rsp+180h+var_140]
0x10047fd4b  call    cs:__imp_?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z; SOS_RingBuffer::StoreRecordInternalWithoutEvent(SOS_RingBufferRecord *,StackFrames<24> *)
0x10047fd51  mov     eax, ebx
0x10047fd53  lea     r11, [rsp+180h+var_20]
0x10047fd5b  mov     rbx, [r11+30h]
0x10047fd5f  mov     rsi, [r11+38h]
0x10047fd63  mov     rdi, [r11+40h]
0x10047fd67  mov     rsp, r11
0x10047fd6a  pop     r15
0x10047fd6c  pop     r14
0x10047fd6e  pop     r13
0x10047fd70  pop     r12
0x10047fd72  pop     rbp
0x10047fd73  retn
```
