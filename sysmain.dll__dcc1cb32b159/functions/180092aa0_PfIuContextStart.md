# PfIuContextStart

- ea: `0x180092aa0`
- end: `0x180092e9b`
- name: `PfIuContextStart`
- size: `1019`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006a020`

## callees

- `0x1800382e0`
- `0x18003c814`
- `0x18003cbe4`
- `0x18003cffc`
- `0x18004e3f4`
- `0x180063eb8`
- `0x180067f88`
- `0x180078746`
- `0x180092aa0`
- `0x1800930b0`
- `0x18009330c`
- `0x1800b173c`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `ntdll!NtPowerInformation` at `0x180092c1c`
- `ntdll!NtPowerInformation` at `0x180092c1c`
- `ntdll!RtlInitUnicodeString` at `0x180092d75`
- `ntdll!RtlInitUnicodeString` at `0x180092d75`
- `ntdll!NtOpenEvent` at `0x180092dae`
- `ntdll!NtOpenEvent` at `0x180092dae`
- `ntdll!RtlNtStatusToDosError` at `0x180092c28`
- `ntdll!RtlNtStatusToDosError` at `0x180092c28`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180092d02`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180092d02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180092c40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180092c40`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180092b9e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180092b9e`

## string_xrefs

- `0x180092bd4`: `PfIuBatteryPaths`

## pseudocode

```c
__int64 __fastcall PfIuContextStart(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  void **v4; // rsi
  unsigned int v5; // ebx
  char *v6; // rbx
  void *v7; // rax
  void *v8; // r14
  int v9; // eax
  int Value; // eax
  LSTATUS v12; // eax
  _DWORD *v13; // rdx
  _DWORD *v14; // rbx
  __int64 v15; // rcx
  LPCRITICAL_SECTION v16; // r10
  __int64 v17; // rcx
  struct _RTL_CRITICAL_SECTION *v18; // r10
  __int64 v19; // rcx
  struct _RTL_CRITICAL_SECTION *v20; // r10
  _BYTE OutputBuffer[4]; // [rsp+30h] [rbp-69h] BYREF
  int v22; // [rsp+34h] [rbp-65h] BYREF
  __int64 CurrentTime; // [rsp+38h] [rbp-61h] BYREF
  __int64 InputBuffer; // [rsp+40h] [rbp-59h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-51h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-21h] BYREF
  _BYTE v27[32]; // [rsp+88h] [rbp-11h] BYREF
  __int64 *v28; // [rsp+A8h] [rbp+Fh]
  __int64 v29; // [rsp+B0h] [rbp+17h]

  InputBuffer = 0;
  OutputBuffer[0] = 0;
  v22 = 0;
  v2 = *(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 1432LL);
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( (unsigned int)PfsRegQueryValue(v2, (unsigned int)L"PfIuDbgFlags", 4, 4, (__int64)&v22) || (v22 & 1) != v22 )
    v22 = 0;
  v4 = (void **)(a1 + 64);
  v5 = PfIuHistoryStoreFileMappingCreate(v3, (_QWORD *)(a1 + 56), (_QWORD *)(a1 + 64));
  if ( !v5 )
  {
    v6 = (char *)*v4;
    if ( !*(_QWORD *)*v4 )
    {
      memset_0(*v4, 0, 0x2BD0u);
      PfIuHistoryInitialize(v6 + 5612);
      v6 = (char *)*v4;
    }
    v5 = PfIuHistoryStoreStart(v6, v22 & 1);
    if ( !v5 )
    {
      v7 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, 0x258u);
      v8 = v7;
      if ( !v7 )
        return 8;
      memset_0(v7, 0, 0x258u);
      *(_DWORD *)(a1 + 96) = PfsGetUnbiasedTickCount();
      v5 = PfsMultiStringContextLoad(a1 + 72, *(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 1432LL), L"PfIuBatteryPaths", 8, 0);
      if ( (v5 & 0xFFFFFFFD) != 0 )
      {
LABEL_13:
        HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v8);
        return v5;
      }
      InputBuffer = 4;
      v9 = NtPowerInformation(SystemPowerStateLogging|0x40, &InputBuffer, 8u, OutputBuffer, 1u);
      if ( v9 < 0 )
      {
        v5 = RtlNtStatusToDosError(v9);
        goto LABEL_13;
      }
      *(_DWORD *)(a1 + 36) = OutputBuffer[0];
      Value = PfsRegQueryValue(
                *(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 1432LL),
                (unsigned int)L"PfIuLastMeasures",
                11,
                16,
                a1 + 20);
      if ( Value )
      {
        if ( Value != 2 )
        {
          if ( (unsigned int)dword_1800D2258 > 2 )
          {
            LODWORD(CurrentTime) = Value;
            v29 = 4;
            v28 = &CurrentTime;
            tlgWriteTransfer_EventWriteTransfer(&dword_1800D2258, byte_1800C5BF1, 0, 0, 3, v27);
          }
          v12 = RegDeleteValueW(*(HKEY *)(*(_QWORD *)&PfSvcGlobals + 1432LL), L"PfIuLastMeasures");
          if ( (unsigned int)dword_1800D2258 > 4 )
          {
            LODWORD(CurrentTime) = v12;
            v29 = 4;
            v28 = &CurrentTime;
            tlgWriteTransfer_EventWriteTransfer(&dword_1800D2258, &unk_1800C5C98, 0, 0, 3, v27);
          }
        }
        *(_OWORD *)(a1 + 20) = *(_OWORD *)((char *)*v4 + 5604 * (*(_DWORD *)*v4 & 1) + 12);
        *(_QWORD *)(a1 + 28) = 0;
      }
      RtlInitUnicodeString(&DestinationString, L"\\KernelObjects\\CadRequestPowerSourcePredictions");
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      NtOpenEvent((PHANDLE)(a1 + 40), 0x120001u, &ObjectAttributes);
      v13 = *v4;
      *(_QWORD *)(a1 + 104) = v8;
      v14 = &v13[1401 * (((unsigned __int8)*v13 - 1) & 1)];
      memcpy_0(v14 + 2, &v13[1401 * (*v13 & 1) + 2], 0x15E4u);
      PfIuRemoveOldBatteries(a1, v14 + 2);
      _InterlockedIncrement64((volatile signed __int64 *)*v4);
      *(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 3712LL) = a1;
      CurrentTime = PfsActionItemGetCurrentTime(v15) + 3000000000LL;
      PfsActionItemQueueEx(v16, 0x33u, (unsigned __int64 *)&CurrentTime, 0);
      CurrentTime = PfsActionItemGetCurrentTime(v17);
      PfsActionItemQueueEx(v18 + 43, 0x35u, (unsigned __int64 *)&CurrentTime, 0);
      CurrentTime = PfsActionItemGetCurrentTime(v19) + 144000000000LL;
      PfsActionItemQueueEx(v20 + 43, 0x34u, (unsigned __int64 *)&CurrentTime, 0);
      return 0;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180092aa0  push    rbp
0x180092aa2  push    rbx
0x180092aa3  push    rsi
0x180092aa4  push    rdi
0x180092aa5  push    r12
0x180092aa7  push    r14
0x180092aa9  lea     rbp, [rsp-2Fh]
0x180092aae  sub     rsp, 0C8h
0x180092ab5  mov     rax, cs:__security_cookie
0x180092abc  xor     rax, rsp
0x180092abf  mov     [rbp+57h+var_38], rax
0x180092ac3  xorps   xmm0, xmm0
0x180092ac6  mov     [rbp+57h+InputBuffer], 0
0x180092ace  mov     rdi, rcx
0x180092ad1  mov     [rbp+57h+OutputBuffer], 0
0x180092ad5  mov     rcx, cs:PfSvcGlobals
0x180092adc  lea     rdx, aPfiudbgflags; "PfIuDbgFlags"
0x180092ae3  xor     eax, eax
0x180092ae5  mov     r12d, 4
0x180092aeb  mov     [rbp+57h+var_BC], eax
0x180092aee  mov     r9d, r12d
0x180092af1  lea     rax, [rbp+57h+var_BC]
0x180092af5  mov     r8d, r12d
0x180092af8  mov     rcx, [rcx+598h]
0x180092aff  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180092b03  mov     qword ptr [rsp+0F0h+OutputBufferLength], rax
0x180092b08  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180092b0c  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180092b10  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180092b14  call    PfsRegQueryValue
0x180092b19  test    eax, eax
0x180092b1b  jnz     short loc_180092B28
0x180092b1d  mov     eax, [rbp+57h+var_BC]
0x180092b20  and     eax, 1
0x180092b23  cmp     eax, [rbp+57h+var_BC]
0x180092b26  jz      short loc_180092B2F
0x180092b28  mov     [rbp+57h+var_BC], 0
0x180092b2f  lea     rsi, [rdi+40h]
0x180092b33  mov     r8, rsi
0x180092b36  lea     rdx, [rdi+38h]
0x180092b3a  call    PfIuHistoryStoreFileMappingCreate
0x180092b3f  mov     ebx, eax
0x180092b41  test    eax, eax
0x180092b43  jnz     loc_180092C46
0x180092b49  mov     rbx, [rsi]
0x180092b4c  cmp     qword ptr [rbx], 0
0x180092b50  jnz     short loc_180092B71
0x180092b52  xor     edx, edx; Val
0x180092b54  mov     r8d, 2BD0h; Size
0x180092b5a  mov     rcx, rbx; void *
0x180092b5d  call    memset_0
0x180092b62  lea     rcx, [rbx+15ECh]
0x180092b69  call    PfIuHistoryInitialize
0x180092b6e  mov     rbx, [rsi]
0x180092b71  mov     edx, [rbp+57h+var_BC]
0x180092b74  mov     rcx, rbx
0x180092b77  and     edx, 1
0x180092b7a  call    PfIuHistoryStoreStart
0x180092b7f  mov     ebx, eax
0x180092b81  test    eax, eax
0x180092b83  jnz     loc_180092C46
0x180092b89  mov     rcx, cs:PfSvcGlobals
0x180092b90  mov     ebx, 258h
0x180092b95  mov     r8d, ebx; dwBytes
0x180092b98  xor     edx, edx; dwFlags
0x180092b9a  mov     rcx, [rcx+58h]; hHeap
0x180092b9e  call    cs:__imp_HeapAlloc
0x180092ba4  mov     r14, rax
0x180092ba7  test    rax, rax
0x180092baa  jnz     short loc_180092BB4
0x180092bac  lea     ebx, [rax+8]
0x180092baf  jmp     loc_180092C46
0x180092bb4  mov     r8, rbx; Size
0x180092bb7  xor     edx, edx; Val
0x180092bb9  mov     rcx, r14; void *
0x180092bbc  call    memset_0
0x180092bc1  call    PfsGetUnbiasedTickCount
0x180092bc6  mov     [rdi+60h], eax
0x180092bc9  lea     rcx, [rdi+48h]
0x180092bcd  mov     rdx, cs:PfSvcGlobals
0x180092bd4  lea     r8, aPfiubatterypat; "PfIuBatteryPaths"
0x180092bdb  mov     r9d, 8
0x180092be1  mov     [rsp+0F0h+OutputBufferLength], 0
0x180092be9  mov     rdx, [rdx+598h]
0x180092bf0  call    PfsMultiStringContextLoad
0x180092bf5  mov     ebx, eax
0x180092bf7  test    eax, 0FFFFFFFDh
0x180092bfc  jnz     short loc_180092C30
0x180092bfe  mov     r8d, 8; InputBufferLength
0x180092c04  mov     [rbp+57h+InputBuffer], r12
0x180092c08  lea     r9, [rbp+57h+OutputBuffer]; OutputBuffer
0x180092c0c  mov     [rsp+0F0h+OutputBufferLength], 1; OutputBufferLength
0x180092c14  lea     rdx, [rbp+57h+InputBuffer]; InputBuffer
0x180092c18  lea     ecx, [r8+4Fh]; PowerInformationLevel
0x180092c1c  call    cs:__imp_NtPowerInformation
0x180092c22  test    eax, eax
0x180092c24  jns     short loc_180092C64
0x180092c26  mov     ecx, eax; Status
0x180092c28  call    cs:__imp_RtlNtStatusToDosError
0x180092c2e  mov     ebx, eax
0x180092c30  mov     rcx, cs:PfSvcGlobals
0x180092c37  mov     r8, r14; lpMem
0x180092c3a  xor     edx, edx; dwFlags
0x180092c3c  mov     rcx, [rcx+58h]; hHeap
0x180092c40  call    cs:__imp_HeapFree
0x180092c46  mov     eax, ebx
0x180092c48  mov     rcx, [rbp+57h+var_38]
0x180092c4c  xor     rcx, rsp; StackCookie
0x180092c4f  call    __security_check_cookie
0x180092c54  add     rsp, 0C8h
0x180092c5b  pop     r14
0x180092c5d  pop     r12
0x180092c5f  pop     rdi
0x180092c60  pop     rsi
0x180092c61  pop     rbx
0x180092c62  pop     rbp
0x180092c63  retn
0x180092c64  movzx   eax, [rbp+57h+OutputBuffer]
0x180092c68  lea     rbx, [rdi+14h]
0x180092c6c  mov     [rdi+24h], eax
0x180092c6f  lea     rdx, aPfiulastmeasur; "PfIuLastMeasures"
0x180092c76  mov     rcx, cs:PfSvcGlobals
0x180092c7d  mov     r9d, 10h
0x180092c83  mov     qword ptr [rsp+0F0h+OutputBufferLength], rbx
0x180092c88  mov     rcx, [rcx+598h]
0x180092c8f  lea     r8d, [r9-5]
0x180092c93  call    PfsRegQueryValue
0x180092c98  test    eax, eax
0x180092c9a  jz      loc_180092D6A
0x180092ca0  cmp     eax, 2
0x180092ca3  jz      loc_180092D4C
0x180092ca9  mov     ecx, cs:dword_1800D2258
0x180092caf  cmp     ecx, 2
0x180092cb2  jbe     short loc_180092CED
0x180092cb4  mov     dword ptr [rbp+57h+var_B8], eax
0x180092cb7  lea     rdx, byte_1800C5BF1
0x180092cbe  lea     rax, [rbp+57h+var_B8]
0x180092cc2  mov     [rbp+57h+var_40], r12
0x180092cc6  mov     [rbp+57h+var_48], rax
0x180092cca  lea     rcx, dword_1800D2258
0x180092cd1  lea     rax, [rbp+57h+var_68]
0x180092cd5  xor     r9d, r9d
0x180092cd8  mov     [rsp+0F0h+var_C8], rax
0x180092cdd  xor     r8d, r8d
0x180092ce0  mov     [rsp+0F0h+OutputBufferLength], 3
0x180092ce8  call    _tlgWriteTransfer_EventWriteTransfer
0x180092ced  mov     rcx, cs:PfSvcGlobals
0x180092cf4  lea     rdx, aPfiulastmeasur; "PfIuLastMeasures"
0x180092cfb  mov     rcx, [rcx+598h]; hKey
0x180092d02  call    cs:__imp_RegDeleteValueW
0x180092d08  mov     ecx, cs:dword_1800D2258
0x180092d0e  cmp     ecx, r12d
0x180092d11  jbe     short loc_180092D4C
0x180092d13  mov     dword ptr [rbp+57h+var_B8], eax
0x180092d16  lea     rdx, unk_1800C5C98
0x180092d1d  lea     rax, [rbp+57h+var_B8]
0x180092d21  mov     [rbp+57h+var_40], r12
0x180092d25  mov     [rbp+57h+var_48], rax
0x180092d29  lea     rcx, dword_1800D2258
0x180092d30  lea     rax, [rbp+57h+var_68]
0x180092d34  xor     r9d, r9d
0x180092d37  mov     [rsp+0F0h+var_C8], rax
0x180092d3c  xor     r8d, r8d
0x180092d3f  mov     [rsp+0F0h+OutputBufferLength], 3
0x180092d47  call    _tlgWriteTransfer_EventWriteTransfer
0x180092d4c  mov     rcx, [rsi]
0x180092d4f  mov     eax, [rcx]
0x180092d51  and     eax, 1
0x180092d54  imul    rax, 15E4h
0x180092d5b  movups  xmm0, xmmword ptr [rax+rcx+0Ch]
0x180092d60  xor     eax, eax
0x180092d62  movdqu  xmmword ptr [rbx], xmm0
0x180092d66  mov     [rdi+1Ch], rax
0x180092d6a  lea     rdx, aKernelobjectsC; "\\KernelObjects\\CadRequestPowerSourceP"...
0x180092d71  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180092d75  call    cs:__imp_RtlInitUnicodeString
0x180092d7b  lea     rax, [rbp+57h+DestinationString]
0x180092d7f  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180092d86  xorps   xmm0, xmm0
0x180092d89  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180092d8d  lea     rcx, [rdi+28h]; EventHandle
0x180092d91  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180092d99  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180092d9d  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x180092da4  mov     edx, 120001h; DesiredAccess
0x180092da9  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180092dae  call    cs:__imp_NtOpenEvent
0x180092db4  mov     rdx, [rsi]
0x180092db7  mov     r8d, 15E4h; Size
0x180092dbd  mov     [rdi+68h], r14
0x180092dc1  mov     ecx, [rdx]
0x180092dc3  lea     eax, [rcx-1]
0x180092dc6  and     ecx, 1
0x180092dc9  and     eax, 1
0x180092dcc  imul    rbx, rax, 15E4h
0x180092dd3  imul    rax, rcx, 15E4h
0x180092dda  add     rbx, rdx
0x180092ddd  add     rdx, 8
0x180092de1  lea     rcx, [rbx+8]; void *
0x180092de5  add     rdx, rax; Src
0x180092de8  call    memcpy_0
0x180092ded  lea     rdx, [rbx+8]
0x180092df1  mov     rcx, rdi
0x180092df4  call    PfIuRemoveOldBatteries
0x180092df9  mov     rax, [rsi]
0x180092dfc  lock inc qword ptr [rax]
0x180092e00  mov     rax, cs:PfSvcGlobals
0x180092e07  mov     [rax+0E80h], rdi
0x180092e0e  lea     r10, [rax+6B8h]
0x180092e15  call    PfsActionItemGetCurrentTime
0x180092e1a  xor     r9d, r9d
0x180092e1d  lea     r8, [rbp+57h+var_B8]
0x180092e21  mov     ecx, 0B2D05E00h
0x180092e26  add     rax, rcx
0x180092e29  mov     rcx, r10; lpCriticalSection
0x180092e2c  mov     [rbp+57h+var_B8], rax
0x180092e30  lea     edx, [r9+33h]
0x180092e34  call    PfsActionItemQueueEx
0x180092e39  mov     r10, cs:PfSvcGlobals
0x180092e40  call    PfsActionItemGetCurrentTime
0x180092e45  xor     r9d, r9d
0x180092e48  mov     [rbp+57h+var_B8], rax
0x180092e4c  lea     r8, [rbp+57h+var_B8]
0x180092e50  lea     rcx, [r10+6B8h]; lpCriticalSection
0x180092e57  lea     edx, [r9+35h]
0x180092e5b  call    PfsActionItemQueueEx
0x180092e60  mov     r10, cs:PfSvcGlobals
0x180092e67  call    PfsActionItemGetCurrentTime
0x180092e6c  xor     r9d, r9d
0x180092e6f  lea     r8, [rbp+57h+var_B8]
0x180092e73  mov     rcx, 218711A000h
0x180092e7d  add     rax, rcx
0x180092e80  lea     rcx, [r10+6B8h]; lpCriticalSection
0x180092e87  mov     [rbp+57h+var_B8], rax
0x180092e8b  lea     edx, [r9+34h]
0x180092e8f  call    PfsActionItemQueueEx
0x180092e94  xor     ebx, ebx
0x180092e96  jmp     loc_180092C46
```
