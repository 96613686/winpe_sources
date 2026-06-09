# ConvertVhdxToVhdSetRsvd

- ea: `0x18000a3f8`
- end: `0x18000a62c`
- name: `ConvertVhdxToVhdSetRsvd`
- size: `564`
- prototype: `__int64 __fastcall(const WCHAR *, const void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000648c`

## callees

- `0x180004110`
- `0x180004ed0`
- `0x180005730`
- `0x18000a27c`
- `0x18000a3f8`
- `0x18000a76c`
- `0x18000b09c`
- `0x18000b30c`
- `0x18000ba11`

## import_xrefs

- `ntdll!NtClose` at `0x18000a54d`
- `ntdll!NtClose` at `0x18000a54d`
- `ntdll!RtlNtStatusToDosError` at `0x18000a619`
- `ntdll!RtlNtStatusToDosError` at `0x18000a619`
- `ntdll!RtlFreeHeap` at `0x18000a515`
- `ntdll!RtlFreeHeap` at `0x18000a538`
- `ntdll!RtlFreeHeap` at `0x18000a515`
- `ntdll!RtlFreeHeap` at `0x18000a538`
- `ntdll!RtlAllocateHeap` at `0x18000a4dc`
- `ntdll!RtlAllocateHeap` at `0x18000a4dc`
- `ntdll!RtlInitUnicodeString` at `0x18000a480`
- `ntdll!RtlInitUnicodeString` at `0x18000a480`

## pseudocode

```c
__int64 __fastcall ConvertVhdxToVhdSetRsvd(const WCHAR *a1, const void **a2)
{
  _DWORD *v2; // rdi
  __int64 v3; // rsi
  __int64 v6; // r8
  __int64 v7; // rdx
  unsigned int v8; // ebx
  size_t v9; // rbx
  int v10; // esi
  _DWORD *Heap; // rax
  __int128 v13; // xmm0
  DWORD v14; // r9d
  NTSTATUS v15; // ecx
  int v16; // [rsp+20h] [rbp-39h]
  DWORD v17; // [rsp+28h] [rbp-31h]
  HANDLE hFile; // [rsp+40h] [rbp-19h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+48h] [rbp-11h] BYREF
  PVOID P[2]; // [rsp+50h] [rbp-9h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp+7h] BYREF
  __int128 v22; // [rsp+70h] [rbp+17h] BYREF

  v2 = 0;
  v3 = -1;
  NumberOfBytesTransferred = 0;
  hFile = (HANDLE)-1LL;
  *(_OWORD *)P = 0;
  DestinationString = 0;
  v22 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_SZ(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2);
  }
  RtlInitUnicodeString(&DestinationString, a1);
  v8 = ConstructRsvdPathToFile(&DestinationString, (struct _UNICODE_STRING *)P, v6);
  if ( !v8 )
  {
    v8 = OpenPathForRsvd(P, v7, &hFile);
    if ( v8 )
    {
LABEL_9:
      v3 = (__int64)hFile;
      goto LABEL_10;
    }
    GenerateUniqueID(&v22);
    v9 = *(unsigned __int16 *)a2 + 2LL;
    v10 = *(unsigned __int16 *)a2 + 50;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, *(unsigned __int16 *)a2 + 50LL);
    v2 = Heap;
    if ( !Heap )
    {
      v8 = 14;
      goto LABEL_9;
    }
    *Heap = 33562881;
    v13 = v22;
    Heap[8] = 4;
    Heap[10] = v9;
    *((_OWORD *)Heap + 1) = v13;
    memcpy_0(Heap + 11, a2[1], v9);
    v14 = v10;
    v17 = v10;
    v3 = (__int64)hFile;
    v8 = IssueSynchronousDeviceIoControl(hFile, 0x90364u, v2, v14, v2, v17, &NumberOfBytesTransferred);
    if ( !v8 )
    {
      v15 = v2[1];
      if ( v15 < 0 )
        v8 = RtlNtStatusToDosError(v15);
    }
  }
LABEL_10:
  if ( P[1] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
  if ( v2 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
  if ( v3 != -1 )
    NtClose((HANDLE)v3);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DdSZ(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, (__int64)a1, (__int64)a2);
  }
  return v8;
}

```

## disassembly

```asm
0x18000a3f8  mov     [rsp-8+arg_10], rbx
0x18000a3fd  mov     [rsp-8+arg_18], rsi
0x18000a402  push    rbp
0x18000a403  push    rdi
0x18000a404  push    r12
0x18000a406  push    r14
0x18000a408  push    r15
0x18000a40a  lea     rbp, [rsp-37h]
0x18000a40f  sub     rsp, 90h
0x18000a416  mov     rax, cs:__security_cookie
0x18000a41d  xor     rax, rsp
0x18000a420  mov     [rbp+57h+var_30], rax
0x18000a424  xor     edi, edi
0x18000a426  xorps   xmm0, xmm0
0x18000a429  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000a42d  mov     [rbp+57h+NumberOfBytesTransferred], edi
0x18000a430  xorps   xmm1, xmm1
0x18000a433  mov     [rbp+57h+hFile], rsi
0x18000a437  mov     r14, rdx
0x18000a43a  mov     r15, rcx
0x18000a43d  movups  xmmword ptr [rbp+57h+P], xmm0
0x18000a441  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18000a445  movups  [rbp+57h+var_40], xmm1
0x18000a449  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a450  lea     r12, WPP_GLOBAL_Control
0x18000a457  cmp     rcx, r12
0x18000a45a  jz      short loc_18000A479
0x18000a45c  test    byte ptr [rcx+1Ch], 20h
0x18000a460  jz      short loc_18000A479
0x18000a462  cmp     byte ptr [rcx+19h], 4
0x18000a466  jb      short loc_18000A479
0x18000a468  mov     rcx, [rcx+10h]; LoggerHandle
0x18000a46c  mov     r9, r15
0x18000a46f  mov     [rsp+0B0h+var_90], rdx; int
0x18000a474  call    WPP_SF_SZ
0x18000a479  mov     rdx, r15; SourceString
0x18000a47c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000a480  call    cs:__imp_RtlInitUnicodeString
0x18000a487  nop     dword ptr [rax+rax+00h]
0x18000a48c  lea     rdx, [rbp+57h+P]; __int64
0x18000a490  lea     rcx, [rbp+57h+DestinationString]; __int64
0x18000a494  call    ConstructRsvdPathToFile
0x18000a499  mov     ebx, eax
0x18000a49b  test    eax, eax
0x18000a49d  jnz     short loc_18000A4FB
0x18000a49f  lea     r8, [rbp+57h+hFile]
0x18000a4a3  lea     rcx, [rbp+57h+P]
0x18000a4a7  call    OpenPathForRsvd
0x18000a4ac  mov     ebx, eax
0x18000a4ae  test    eax, eax
0x18000a4b0  jnz     short loc_18000A4F7
0x18000a4b2  lea     rcx, [rbp+57h+var_40]
0x18000a4b6  call    GenerateUniqueID
0x18000a4bb  movzx   ebx, word ptr [r14]
0x18000a4bf  mov     edx, 8; Flags
0x18000a4c4  mov     rcx, gs:60h
0x18000a4cd  add     rbx, 2
0x18000a4d1  mov     rcx, [rcx+30h]; HeapHandle
0x18000a4d5  lea     rsi, [rbx+30h]
0x18000a4d9  mov     r8, rsi; Size
0x18000a4dc  call    cs:__imp_RtlAllocateHeap
0x18000a4e3  nop     dword ptr [rax+rax+00h]
0x18000a4e8  mov     rdi, rax
0x18000a4eb  test    rax, rax
0x18000a4ee  jnz     loc_18000A5B2
0x18000a4f4  lea     ebx, [rax+0Eh]
0x18000a4f7  mov     rsi, [rbp+57h+hFile]
0x18000a4fb  cmp     [rbp+57h+P+8], 0
0x18000a500  jz      short loc_18000A521
0x18000a502  mov     rcx, gs:60h
0x18000a50b  xor     edx, edx; Flags
0x18000a50d  mov     r8, [rbp+57h+P+8]; P
0x18000a511  mov     rcx, [rcx+30h]; HeapHandle
0x18000a515  call    cs:__imp_RtlFreeHeap
0x18000a51c  nop     dword ptr [rax+rax+00h]
0x18000a521  test    rdi, rdi
0x18000a524  jz      short loc_18000A544
0x18000a526  mov     rcx, gs:60h
0x18000a52f  mov     r8, rdi; P
0x18000a532  xor     edx, edx; Flags
0x18000a534  mov     rcx, [rcx+30h]; HeapHandle
0x18000a538  call    cs:__imp_RtlFreeHeap
0x18000a53f  nop     dword ptr [rax+rax+00h]
0x18000a544  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000a548  jz      short loc_18000A559
0x18000a54a  mov     rcx, rsi; Handle
0x18000a54d  call    cs:__imp_NtClose
0x18000a554  nop     dword ptr [rax+rax+00h]
0x18000a559  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a560  cmp     rcx, r12
0x18000a563  jz      short loc_18000A587
0x18000a565  test    byte ptr [rcx+1Ch], 20h
0x18000a569  jz      short loc_18000A587
0x18000a56b  cmp     byte ptr [rcx+19h], 4
0x18000a56f  jb      short loc_18000A587
0x18000a571  mov     rcx, [rcx+10h]; LoggerHandle
0x18000a575  mov     r9d, ebx
0x18000a578  mov     [rsp+0B0h+lpNumberOfBytesTransferred], r14; __int64
0x18000a57d  mov     qword ptr [rsp+0B0h+var_88], r15; __int64
0x18000a582  call    WPP_SF_DdSZ
0x18000a587  mov     eax, ebx
0x18000a589  mov     rcx, [rbp+57h+var_30]
0x18000a58d  xor     rcx, rsp; StackCookie
0x18000a590  call    __security_check_cookie
0x18000a595  lea     r11, [rsp+0B0h+var_20]
0x18000a59d  mov     rbx, [r11+40h]
0x18000a5a1  mov     rsi, [r11+48h]
0x18000a5a5  mov     rsp, r11
0x18000a5a8  pop     r15
0x18000a5aa  pop     r14
0x18000a5ac  pop     r12
0x18000a5ae  pop     rdi
0x18000a5af  pop     rbp
0x18000a5b0  retn
0x18000a5b2  mov     dword ptr [rax], 2002101h
0x18000a5b8  lea     rcx, [rax+2Ch]; void *
0x18000a5bc  movups  xmm0, [rbp+57h+var_40]
0x18000a5c0  mov     dword ptr [rax+20h], 4
0x18000a5c7  mov     r8, rbx; Size
0x18000a5ca  mov     [rax+28h], ebx
0x18000a5cd  movdqu  xmmword ptr [rax+10h], xmm0
0x18000a5d2  mov     rdx, [r14+8]; Src
0x18000a5d6  call    memcpy_0
0x18000a5db  lea     rax, [rbp+57h+NumberOfBytesTransferred]
0x18000a5df  mov     r9d, esi; nInBufferSize
0x18000a5e2  mov     [rsp+0B0h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x18000a5e7  mov     r8, rdi; lpInBuffer
0x18000a5ea  mov     [rsp+0B0h+var_88], esi; DWORD
0x18000a5ee  mov     edx, 90364h; dwIoControlCode
0x18000a5f3  mov     rsi, [rbp+57h+hFile]
0x18000a5f7  mov     rcx, rsi; hFile
0x18000a5fa  mov     [rsp+0B0h+var_90], rdi; LPVOID
0x18000a5ff  call    IssueSynchronousDeviceIoControl
0x18000a604  mov     ebx, eax
0x18000a606  test    eax, eax
0x18000a608  jnz     loc_18000A4FB
0x18000a60e  mov     ecx, [rdi+4]; Status
0x18000a611  test    ecx, ecx
0x18000a613  jns     loc_18000A4FB
0x18000a619  call    cs:__imp_RtlNtStatusToDosError
0x18000a620  nop     dword ptr [rax+rax+00h]
0x18000a625  mov     ebx, eax
0x18000a627  jmp     loc_18000A4FB
```
