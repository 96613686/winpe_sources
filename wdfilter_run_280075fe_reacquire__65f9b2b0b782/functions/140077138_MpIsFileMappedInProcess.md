# MpIsFileMappedInProcess

- ea: `0x140077138`
- end: `0x1400772de`
- name: `MpIsFileMappedInProcess`
- size: `422`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String1, PVOID Object)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14007451c`

## callees

- `0x1400118d0`
- `0x140011bc0`
- `0x140077138`
- `0x140080090`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x1400771f5`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400771f5`
- `ntoskrnl!PsProcessType` at `0x1400771da`
- `ntoskrnl!ZwQueryVirtualMemory` at `0x14007721f`
- `ntoskrnl!ZwQueryVirtualMemory` at `0x14007721f`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400771ab`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400771ab`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14007726b`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14007726b`
- `ntoskrnl!ZwClose` at `0x1400772a5`
- `ntoskrnl!ZwClose` at `0x1400772a5`

## pseudocode

```c
char __fastcall MpIsFileMappedInProcess(PCUNICODE_STRING String1, PEPROCESS Object, unsigned __int64 a3)
{
  char v3; // bl
  unsigned __int64 v4; // rsi
  unsigned __int64 v7; // rdi
  HANDLE ProcessHandle; // [rsp+40h] [rbp-C0h] BYREF
  __int128 MemoryInformation; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v11; // [rsp+58h] [rbp-A8h]
  __int128 v12; // [rsp+68h] [rbp-98h]
  UNICODE_STRING String2[34]; // [rsp+80h] [rbp-80h] BYREF

  v3 = 0;
  ProcessHandle = 0;
  v4 = a3;
  MemoryInformation = 0;
  v11 = 0;
  v12 = 0;
  if ( !String1 || !Object )
    return 0;
  v7 = 0x10000;
  if ( a3 - 1 <= 0xFFFF )
    v4 = 0;
  if ( Object == IoGetCurrentProcess() )
    ProcessHandle = (HANDLE)-1LL;
  else
    ObOpenObjectByPointer(Object, 0x200u, 0, 0x1418u, (POBJECT_TYPE)PsProcessType, 0, &ProcessHandle);
  while ( ZwQueryVirtualMemory(ProcessHandle, (PVOID)v7, MemoryBasicInformation, &MemoryInformation, 0x30u, 0) >= 0 )
  {
    if ( DWORD2(v12) == 0x40000 )
    {
      memset(String2, 0, 0x218u);
      if ( (int)MpGetMappedFileName(ProcessHandle, MemoryInformation, String2) >= 0
        && !RtlCompareUnicodeString(String1, String2, 1u) )
      {
        v3 = 1;
        break;
      }
    }
    v7 += *((_QWORD *)&v11 + 1);
    if ( v4 && v7 >= v4 )
      break;
  }
  if ( (char *)ProcessHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    ZwClose(ProcessHandle);
  return v3;
}

```

## disassembly

```asm
0x140077138  mov     [rsp-8+arg_10], rbx
0x14007713d  push    rbp
0x14007713e  push    rsi
0x14007713f  push    rdi
0x140077140  push    r14
0x140077142  push    r15
0x140077144  lea     rbp, [rsp-1B0h]
0x14007714c  sub     rsp, 2B0h
0x140077153  mov     rax, cs:__security_cookie
0x14007715a  xor     rax, rsp
0x14007715d  mov     [rbp+1D0h+var_30], rax
0x140077164  xorps   xmm0, xmm0
0x140077167  xor     ebx, ebx
0x140077169  mov     [rsp+2D0h+ProcessHandle], rbx
0x14007716e  mov     rsi, r8
0x140077171  mov     r14, rdx
0x140077174  mov     r15, rcx
0x140077177  movups  [rsp+2D0h+MemoryInformation], xmm0
0x14007717c  movups  [rsp+2D0h+var_278], xmm0
0x140077181  movups  [rsp+2D0h+var_268], xmm0
0x140077186  test    rcx, rcx
0x140077189  jz      loc_1400772B5
0x14007718f  test    rdx, rdx
0x140077192  jz      loc_1400772B5
0x140077198  lea     rax, [r8-1]
0x14007719c  mov     edi, 10000h
0x1400771a1  cmp     rax, 0FFFFh
0x1400771a7  cmovbe  rsi, rbx
0x1400771ab  call    cs:__imp_IoGetCurrentProcess
0x1400771b2  nop     dword ptr [rax+rax+00h]
0x1400771b7  cmp     r14, rax
0x1400771ba  jnz     short loc_1400771C7
0x1400771bc  mov     [rsp+2D0h+ProcessHandle], 0FFFFFFFFFFFFFFFFh
0x1400771c5  jmp     short loc_140077201
0x1400771c7  lea     rax, [rsp+2D0h+ProcessHandle]
0x1400771cc  mov     r9d, 1418h; DesiredAccess
0x1400771d2  mov     [rsp+2D0h+Handle], rax; Handle
0x1400771d7  xor     r8d, r8d; PassedAccessState
0x1400771da  mov     rax, cs:__imp_PsProcessType
0x1400771e1  mov     rcx, r14; Object
0x1400771e4  mov     [rsp+2D0h+AccessMode], bl; AccessMode
0x1400771e8  mov     rdx, [rax]
0x1400771eb  mov     [rsp+2D0h+ObjectType], rdx; ObjectType
0x1400771f0  mov     edx, 200h; HandleAttributes
0x1400771f5  call    cs:__imp_ObOpenObjectByPointer
0x1400771fc  nop     dword ptr [rax+rax+00h]
0x140077201  mov     rcx, [rsp+2D0h+ProcessHandle]; ProcessHandle
0x140077206  lea     r9, [rsp+2D0h+MemoryInformation]; MemoryInformation
0x14007720b  mov     qword ptr [rsp+2D0h+AccessMode], rbx; ReturnLength
0x140077210  xor     r8d, r8d; MemoryInformationClass
0x140077213  mov     rdx, rdi; BaseAddress
0x140077216  mov     [rsp+2D0h+ObjectType], 30h ; '0'; MemoryInformationLength
0x14007721f  call    cs:__imp_ZwQueryVirtualMemory
0x140077226  nop     dword ptr [rax+rax+00h]
0x14007722b  test    eax, eax
0x14007722d  js      short loc_140077296
0x14007722f  cmp     dword ptr [rsp+2D0h+var_268+8], 40000h
0x140077237  jnz     short loc_14007727B
0x140077239  xor     edx, edx; Val
0x14007723b  lea     rcx, [rbp+1D0h+String2]; void *
0x14007723f  mov     r8d, 218h; Size
0x140077245  call    memset
0x14007724a  mov     rdx, qword ptr [rsp+2D0h+MemoryInformation]
0x14007724f  lea     r8, [rbp+1D0h+String2]
0x140077253  mov     rcx, [rsp+2D0h+ProcessHandle]
0x140077258  call    MpGetMappedFileName
0x14007725d  test    eax, eax
0x14007725f  js      short loc_14007727B
0x140077261  mov     r8b, 1; CaseInSensitive
0x140077264  lea     rdx, [rbp+1D0h+String2]; String2
0x140077268  mov     rcx, r15; String1
0x14007726b  call    cs:__imp_RtlCompareUnicodeString
0x140077272  nop     dword ptr [rax+rax+00h]
0x140077277  test    eax, eax
0x140077279  jz      short loc_140077294
0x14007727b  add     rdi, qword ptr [rsp+2D0h+var_278+8]
0x140077280  test    rsi, rsi
0x140077283  jz      loc_140077201
0x140077289  cmp     rdi, rsi
0x14007728c  jb      loc_140077201
0x140077292  jmp     short loc_140077296
0x140077294  mov     bl, 1
0x140077296  mov     rcx, [rsp+2D0h+ProcessHandle]; Handle
0x14007729b  lea     rdx, [rcx-1]
0x14007729f  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1400772a3  ja      short loc_1400772B1
0x1400772a5  call    cs:__imp_ZwClose
0x1400772ac  nop     dword ptr [rax+rax+00h]
0x1400772b1  mov     al, bl
0x1400772b3  jmp     short loc_1400772B7
0x1400772b5  xor     al, al
0x1400772b7  mov     rcx, [rbp+1D0h+var_30]
0x1400772be  xor     rcx, rsp; StackCookie
0x1400772c1  call    __security_check_cookie
0x1400772c6  mov     rbx, [rsp+2D0h+arg_10]
0x1400772ce  add     rsp, 2B0h
0x1400772d5  pop     r15
0x1400772d7  pop     r14
0x1400772d9  pop     rdi
0x1400772da  pop     rsi
0x1400772db  pop     rbp
0x1400772dc  retn
```
