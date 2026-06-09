# SoftAPMgrInit(ulong,void *,_SOFTAP_CALLBACKS *,_SOFTAP_MANAGER * *)

- ea: `0x18008ba08`
- end: `0x18008bc70`
- name: `?SoftAPMgrInit@@YAKKPEAXPEAU_SOFTAP_CALLBACKS@@PEAPEAU_SOFTAP_MANAGER@@@Z`
- size: `616`
- prototype: `unsigned int __fastcall(unsigned int, void *, struct _SOFTAP_CALLBACKS *, struct _SOFTAP_MANAGER **)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18008b7e0`
- `0x1800b367c`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x18002f450`
- `0x18008ba08`
- `0x1800c6774`
- `0x180107330`
- `0x18019c3d4`
- `0x18019cd8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18008bae5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18008bae5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008bb2b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008bb8d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008bb2b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008bb8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bb3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bb9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bb3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bb9f`

## pseudocode

```c
__int64 __fastcall SoftAPMgrInit(
        unsigned int a1,
        void *a2,
        struct _SOFTAP_CALLBACKS *a3,
        struct _RTL_CRITICAL_SECTION **a4)
{
  PVOID v6; // rcx
  struct _RTL_CRITICAL_SECTION *v7; // rax
  struct _RTL_CRITICAL_SECTION *v8; // rdi
  unsigned int v9; // ebx
  PVOID *v10; // rcx
  int v11; // eax
  HANDLE EventW; // rax
  DWORD LastError; // eax
  __int64 v14; // r8
  __int64 v15; // rdx
  HANDLE v16; // rax

  *a4 = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 10, &WPP_947d07f958fb38b15e01080ffbf9c4a9_Traceguids);
  }
  if ( a1 != 8 && a1 != 32 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6, a2, a3);
  v7 = (struct _RTL_CRITICAL_SECTION *)AllocWLMem(0x150u);
  v8 = v7;
  if ( v7 )
  {
    memset_0(v7, 0, 0x150u);
    InitializeCriticalSection(v8);
    LODWORD(v8[1].DebugInfo) = 1;
    HIDWORD(v8[1].DebugInfo) = a1;
    v11 = 2;
    if ( a1 != 8 )
      v11 = 16;
    v8[1].LockCount = v11;
    LODWORD(v8[6].SpinCount) = 0;
    LODWORD(v8[1].SpinCount) = 0;
    v8[1].RecursionCount = 0;
    EventW = CreateEventW(0, 0, 0, 0);
    v8[7].OwningThread = EventW;
    if ( EventW )
    {
      v16 = CreateEventW(0, 0, 0, 0);
      v8[7].LockSemaphore = v16;
      if ( v16 )
      {
        v9 = 0;
        *a4 = v8;
        v8 = 0;
        goto LABEL_13;
      }
      LastError = GetLastError();
      v9 = LastError;
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_28;
      }
      v15 = 14;
    }
    else
    {
      LastError = GetLastError();
      v9 = LastError;
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_28;
      }
      v15 = 13;
    }
    WPP_SF_dL(v10[12], v15, v14, a1, LastError);
    goto LABEL_13;
  }
  v9 = 14;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105)
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 11, &WPP_947d07f958fb38b15e01080ffbf9c4a9_Traceguids, a1);
LABEL_13:
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_28:
  if ( v9 )
  {
    SoftAPMgrDeinit((struct _SOFTAP_MANAGER *)v8);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && *((_BYTE *)v10 + 105) >= 4u && (*((_BYTE *)v10 + 108) & 1) != 0 )
    WPP_SF_d(v10[12], 15, &WPP_947d07f958fb38b15e01080ffbf9c4a9_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18008ba08  mov     [rsp+arg_0], rbx
0x18008ba0d  mov     [rsp+arg_8], rsi
0x18008ba12  mov     [rsp+arg_10], r8
0x18008ba17  push    rdi
0x18008ba18  push    r14
0x18008ba1a  push    r15
0x18008ba1c  sub     rsp, 30h
0x18008ba20  mov     r15, r9
0x18008ba23  mov     r14d, ecx
0x18008ba26  mov     qword ptr [r9], 0
0x18008ba2d  lea     rsi, WPP_GLOBAL_Control
0x18008ba34  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ba3b  cmp     rcx, rsi
0x18008ba3e  jz      short loc_18008BA61
0x18008ba40  cmp     byte ptr [rcx+69h], 4
0x18008ba44  jb      short loc_18008BA61
0x18008ba46  test    byte ptr [rcx+6Ch], 1
0x18008ba4a  jz      short loc_18008BA61
0x18008ba4c  mov     edx, 0Ah
0x18008ba51  lea     r8, WPP_947d07f958fb38b15e01080ffbf9c4a9_Traceguids
0x18008ba58  mov     rcx, [rcx+60h]
0x18008ba5c  call    WPP_SF_
0x18008ba61  cmp     r14d, 8
0x18008ba65  jz      short loc_18008BA72
0x18008ba67  cmp     r14d, 20h ; ' '
0x18008ba6b  jz      short loc_18008BA72
0x18008ba6d  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "(uCurrentOpMode == 0x00000008) || (uCurrentOpMode == 0x00000020)")
0x18008ba72  mov     ebx, 150h
0x18008ba77  mov     ecx, ebx; dwBytes
0x18008ba79  call    AllocWLMem
0x18008ba7e  mov     rdi, rax
0x18008ba81  mov     [rsp+48h+arg_10], rax
0x18008ba86  test    rax, rax
0x18008ba89  jnz     short loc_18008BAD4
0x18008ba8b  lea     ebx, [rax+0Eh]
0x18008ba8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ba95  cmp     rcx, rsi
0x18008ba98  jz      loc_18008BC1E
0x18008ba9e  cmp     byte ptr [rcx+69h], 1
0x18008baa2  jb      loc_18008BC1E
0x18008baa8  test    byte ptr [rcx+6Ch], 1
0x18008baac  jz      loc_18008BC1E
0x18008bab2  lea     edx, [rax+0Bh]
0x18008bab5  mov     r9d, r14d
0x18008bab8  lea     r8, WPP_947d07f958fb38b15e01080ffbf9c4a9_Traceguids
0x18008babf  mov     rcx, [rcx+60h]
0x18008bac3  call    WPP_SF_d
0x18008bac8  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bacf  jmp     loc_18008BC1E
0x18008bad4  mov     r8, rbx; Size
0x18008bad7  xor     edx, edx; Val
0x18008bad9  mov     rcx, rdi; void *
0x18008badc  call    memset_0
0x18008bae1  nop
0x18008bae2  mov     rcx, rdi; lpCriticalSection
0x18008bae5  call    cs:__imp_InitializeCriticalSection
0x18008baeb  nop
0x18008baec  mov     dword ptr [rdi+28h], 1
0x18008baf3  mov     [rdi+2Ch], r14d
0x18008baf7  mov     eax, 2
0x18008bafc  lea     ecx, [rax+0Eh]
0x18008baff  cmp     r14d, 8
0x18008bb03  cmovnz  eax, ecx
0x18008bb06  mov     [rdi+30h], eax
0x18008bb09  mov     dword ptr [rdi+110h], 0
0x18008bb13  mov     dword ptr [rdi+48h], 0
0x18008bb1a  mov     dword ptr [rdi+34h], 0
0x18008bb21  xor     r9d, r9d; lpName
0x18008bb24  xor     r8d, r8d; bInitialState
0x18008bb27  xor     edx, edx; bManualReset
0x18008bb29  xor     ecx, ecx; lpEventAttributes
0x18008bb2b  call    cs:__imp_CreateEventW
0x18008bb31  mov     [rdi+128h], rax
0x18008bb38  test    rax, rax
0x18008bb3b  jnz     short loc_18008BB83
0x18008bb3d  call    cs:__imp_GetLastError
0x18008bb43  mov     ebx, eax
0x18008bb45  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bb4c  cmp     rcx, rsi
0x18008bb4f  jz      loc_18008BC1E
0x18008bb55  cmp     byte ptr [rcx+69h], 1
0x18008bb59  jb      loc_18008BC1E
0x18008bb5f  test    byte ptr [rcx+6Ch], 1
0x18008bb63  jz      loc_18008BC1E
0x18008bb69  mov     edx, 0Dh
0x18008bb6e  mov     [rsp+48h+var_28], eax
0x18008bb72  mov     r9d, r14d
0x18008bb75  mov     rcx, [rcx+60h]
0x18008bb79  call    WPP_SF_dL
0x18008bb7e  jmp     loc_18008BAC8
0x18008bb83  xor     r9d, r9d; lpName
0x18008bb86  xor     r8d, r8d; bInitialState
0x18008bb89  xor     edx, edx; bManualReset
0x18008bb8b  xor     ecx, ecx; lpEventAttributes
0x18008bb8d  call    cs:__imp_CreateEventW
0x18008bb93  mov     [rdi+130h], rax
0x18008bb9a  test    rax, rax
0x18008bb9d  jnz     short loc_18008BBC6
0x18008bb9f  call    cs:__imp_GetLastError
0x18008bba5  mov     ebx, eax
0x18008bba7  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bbae  cmp     rcx, rsi
0x18008bbb1  jz      short loc_18008BC1E
0x18008bbb3  cmp     byte ptr [rcx+69h], 1
0x18008bbb7  jb      short loc_18008BC1E
0x18008bbb9  test    byte ptr [rcx+6Ch], 1
0x18008bbbd  jz      short loc_18008BC1E
0x18008bbbf  mov     edx, 0Eh
0x18008bbc4  jmp     short loc_18008BB6E
0x18008bbc6  xor     ebx, ebx
0x18008bbc8  mov     [r15], rdi
0x18008bbcb  xor     edi, edi
0x18008bbcd  jmp     loc_18008BAC8
0x18008bbd2  mov     ebx, eax
0x18008bbd4  lea     rax, WPP_GLOBAL_Control
0x18008bbdb  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bbe2  cmp     rcx, rax
0x18008bbe5  jz      short loc_18008BC12
0x18008bbe7  cmp     byte ptr [rcx+69h], 1
0x18008bbeb  jb      short loc_18008BC12
0x18008bbed  test    byte ptr [rcx+6Ch], 1
0x18008bbf1  jz      short loc_18008BC12
0x18008bbf3  mov     edx, 0Ch
0x18008bbf8  mov     r9d, ebx
0x18008bbfb  lea     r8, WPP_947d07f958fb38b15e01080ffbf9c4a9_Traceguids
0x18008bc02  mov     rcx, [rcx+60h]
0x18008bc06  call    WPP_SF_d
0x18008bc0b  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bc12  lea     rsi, WPP_GLOBAL_Control
0x18008bc19  mov     rdi, [rsp+48h+arg_10]
0x18008bc1e  test    ebx, ebx
0x18008bc20  jz      short loc_18008BC31
0x18008bc22  mov     rcx, rdi; struct _SOFTAP_MANAGER *
0x18008bc25  call    ?SoftAPMgrDeinit@@YAXPEAU_SOFTAP_MANAGER@@@Z; SoftAPMgrDeinit(_SOFTAP_MANAGER *)
0x18008bc2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bc31  cmp     rcx, rsi
0x18008bc34  jz      short loc_18008BC5A
0x18008bc36  cmp     byte ptr [rcx+69h], 4
0x18008bc3a  jb      short loc_18008BC5A
0x18008bc3c  test    byte ptr [rcx+6Ch], 1
0x18008bc40  jz      short loc_18008BC5A
0x18008bc42  mov     edx, 0Fh
0x18008bc47  mov     r9d, ebx
0x18008bc4a  lea     r8, WPP_947d07f958fb38b15e01080ffbf9c4a9_Traceguids
0x18008bc51  mov     rcx, [rcx+60h]
0x18008bc55  call    WPP_SF_d
0x18008bc5a  mov     eax, ebx
0x18008bc5c  mov     rbx, [rsp+48h+arg_0]
0x18008bc61  mov     rsi, [rsp+48h+arg_8]
0x18008bc66  add     rsp, 30h
0x18008bc6a  pop     r15
0x18008bc6c  pop     r14
0x18008bc6e  pop     rdi
0x18008bc6f  retn
```
