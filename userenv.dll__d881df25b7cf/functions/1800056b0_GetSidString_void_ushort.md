# GetSidString(void *,ushort * *)

- ea: `0x1800056b0`
- end: `0x1800058f9`
- name: `?GetSidString@@YAJPEAXPEAPEAG@Z`
- size: `585`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800046ac`
- `0x180004968`

## callees

- `0x180005690`
- `0x1800056b0`
- `0x180005900`
- `0x180005b30`
- `0x18001408c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800057bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005819`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800057bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005819`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800056ea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005769`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800056ea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005769`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800056d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005752`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800057a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005805`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800056d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005752`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800057a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005805`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005723`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800058a5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005723`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800058a5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180005740`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180005740`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000578b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000578b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800057e6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800057e6`

## pseudocode

```c
__int64 __fastcall GetSidString(HANDLE TokenHandle, unsigned __int16 **a2)
{
  HANDLE ProcessHeap; // rax
  LPWSTR v5; // rbx
  void *v6; // rsi
  int Error; // edi
  DWORD LengthSid; // edi
  HANDLE v9; // rax
  void *v10; // rax
  void *v11; // rbp
  HANDLE v12; // rax
  int v13; // ebx
  HANDLE v14; // rax
  int v16; // eax
  BOOL TokenInformation; // eax
  DWORD TokenInformationLength; // [rsp+60h] [rbp+18h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp+20h] BYREF

  TokenInformationLength = 200;
  ProcessHeap = GetProcessHeap();
  StringSid = (LPWSTR)HeapAlloc(ProcessHeap, 8u, 0xC8u);
  v5 = StringSid;
  if ( !StringSid )
    return (unsigned int)-2147024882;
  v6 = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, StringSid, TokenInformationLength, &TokenInformationLength) )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error == -2147024774 )
    {
      v16 = ResultFromHeapReAlloc(v5, TokenInformationLength, (void **)&StringSid);
      v5 = StringSid;
      Error = v16;
      if ( v16 < 0 )
        goto LABEL_9;
      TokenInformation = GetTokenInformation(
                           TokenHandle,
                           TokenUser,
                           StringSid,
                           TokenInformationLength,
                           &TokenInformationLength);
      Error = ResultFromWin32Bool(TokenInformation);
    }
  }
  if ( Error >= 0 )
  {
    LengthSid = GetLengthSid(*(PSID *)v5);
    TokenInformationLength = LengthSid;
    v9 = GetProcessHeap();
    v10 = HeapAlloc(v9, 8u, LengthSid);
    v11 = v10;
    if ( !v10 )
    {
      Error = -2147024882;
      goto LABEL_9;
    }
    if ( CopySid(TokenInformationLength, v10, *(PSID *)v5) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
        ResultFromHeapFree(v11);
        goto LABEL_9;
      }
    }
    v6 = v11;
  }
LABEL_9:
  if ( v5 )
  {
    v12 = GetProcessHeap();
    if ( !HeapFree(v12, 0, v5) )
      ResultFromKnownLastError();
  }
  if ( Error < 0 )
    return (unsigned int)Error;
  StringSid = 0;
  if ( ConvertSidToStringSidW(v6, &StringSid) )
  {
    v13 = 0;
  }
  else
  {
    v13 = ResultFromKnownLastError();
    if ( v13 < 0 )
      goto LABEL_16;
  }
  *a2 = StringSid;
LABEL_16:
  if ( v6 )
  {
    v14 = GetProcessHeap();
    if ( !HeapFree(v14, 0, v6) )
      ResultFromKnownLastError();
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800056b0  mov     [rsp+arg_0], rbx
0x1800056b5  mov     [rsp+arg_8], rbp
0x1800056ba  push    rsi
0x1800056bb  push    rdi
0x1800056bc  push    r14
0x1800056be  sub     rsp, 30h
0x1800056c2  mov     r14, rdx
0x1800056c5  mov     [rsp+48h+TokenInformationLength], 0C8h
0x1800056cd  mov     rbp, rcx
0x1800056d0  call    cs:__imp_GetProcessHeap
0x1800056d7  nop     dword ptr [rax+rax+00h]
0x1800056dc  mov     edx, 8; dwFlags
0x1800056e1  mov     r8d, 0C8h; dwBytes
0x1800056e7  mov     rcx, rax; hHeap
0x1800056ea  call    cs:__imp_HeapAlloc
0x1800056f1  nop     dword ptr [rax+rax+00h]
0x1800056f6  mov     [rsp+48h+StringSid], rax
0x1800056fb  mov     rbx, rax
0x1800056fe  test    rax, rax
0x180005701  jz      loc_180005843
0x180005707  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18000570c  lea     rax, [rsp+48h+TokenInformationLength]
0x180005711  mov     r8, rbx; TokenInformation
0x180005714  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180005719  mov     edx, 1; TokenInformationClass
0x18000571e  mov     rcx, rbp; TokenHandle
0x180005721  xor     esi, esi
0x180005723  call    cs:__imp_GetTokenInformation
0x18000572a  nop     dword ptr [rax+rax+00h]
0x18000572f  test    eax, eax
0x180005731  jz      loc_180005859
0x180005737  xor     edi, edi
0x180005739  test    edi, edi
0x18000573b  js      short loc_1800057A4
0x18000573d  mov     rcx, [rbx]; pSid
0x180005740  call    cs:__imp_GetLengthSid
0x180005747  nop     dword ptr [rax+rax+00h]
0x18000574c  mov     edi, eax
0x18000574e  mov     [rsp+48h+TokenInformationLength], edi
0x180005752  call    cs:__imp_GetProcessHeap
0x180005759  nop     dword ptr [rax+rax+00h]
0x18000575e  mov     r8d, edi; dwBytes
0x180005761  mov     edx, 8; dwFlags
0x180005766  mov     rcx, rax; hHeap
0x180005769  call    cs:__imp_HeapAlloc
0x180005770  nop     dword ptr [rax+rax+00h]
0x180005775  mov     rbp, rax
0x180005778  test    rax, rax
0x18000577b  jz      loc_1800058DB
0x180005781  mov     r8, [rbx]; pSourceSid
0x180005784  mov     rdx, rax; pDestinationSid
0x180005787  mov     ecx, [rsp+48h+TokenInformationLength]; nDestinationSidLength
0x18000578b  call    cs:__imp_CopySid
0x180005792  nop     dword ptr [rax+rax+00h]
0x180005797  test    eax, eax
0x180005799  jz      loc_1800058BF
0x18000579f  xor     edi, edi
0x1800057a1  mov     rsi, rbp
0x1800057a4  test    rbx, rbx
0x1800057a7  jz      short loc_1800057D1
0x1800057a9  call    cs:__imp_GetProcessHeap
0x1800057b0  nop     dword ptr [rax+rax+00h]
0x1800057b5  mov     r8, rbx; lpMem
0x1800057b8  xor     edx, edx; dwFlags
0x1800057ba  mov     rcx, rax; hHeap
0x1800057bd  call    cs:__imp_HeapFree
0x1800057c4  nop     dword ptr [rax+rax+00h]
0x1800057c9  test    eax, eax
0x1800057cb  jz      loc_1800058E5
0x1800057d1  test    edi, edi
0x1800057d3  js      short loc_180005848
0x1800057d5  lea     rdx, [rsp+48h+StringSid]; StringSid
0x1800057da  mov     [rsp+48h+StringSid], 0
0x1800057e3  mov     rcx, rsi; Sid
0x1800057e6  call    cs:__imp_ConvertSidToStringSidW
0x1800057ed  nop     dword ptr [rax+rax+00h]
0x1800057f2  test    eax, eax
0x1800057f4  jz      short loc_18000584C
0x1800057f6  xor     ebx, ebx
0x1800057f8  mov     rax, [rsp+48h+StringSid]
0x1800057fd  mov     [r14], rax
0x180005800  test    rsi, rsi
0x180005803  jz      short loc_18000582D
0x180005805  call    cs:__imp_GetProcessHeap
0x18000580c  nop     dword ptr [rax+rax+00h]
0x180005811  mov     r8, rsi; lpMem
0x180005814  xor     edx, edx; dwFlags
0x180005816  mov     rcx, rax; hHeap
0x180005819  call    cs:__imp_HeapFree
0x180005820  nop     dword ptr [rax+rax+00h]
0x180005825  test    eax, eax
0x180005827  jz      loc_1800058EF
0x18000582d  mov     eax, ebx
0x18000582f  mov     rbx, [rsp+48h+arg_0]
0x180005834  mov     rbp, [rsp+48h+arg_8]
0x180005839  add     rsp, 30h
0x18000583d  pop     r14
0x18000583f  pop     rdi
0x180005840  pop     rsi
0x180005841  retn
0x180005843  mov     edi, 8007000Eh
0x180005848  mov     eax, edi
0x18000584a  jmp     short loc_18000582F
0x18000584c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180005851  mov     ebx, eax
0x180005853  test    eax, eax
0x180005855  jns     short loc_1800057F8
0x180005857  jmp     short loc_180005800
0x180005859  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000585e  mov     edi, eax
0x180005860  cmp     eax, 8007007Ah
0x180005865  jnz     loc_180005739
0x18000586b  mov     edx, [rsp+48h+TokenInformationLength]; dwBytes
0x18000586f  lea     r8, [rsp+48h+StringSid]; void **
0x180005874  mov     rcx, rbx; lpMem
0x180005877  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x18000587c  mov     rbx, [rsp+48h+StringSid]
0x180005881  mov     edi, eax
0x180005883  test    eax, eax
0x180005885  js      loc_1800057A4
0x18000588b  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180005890  lea     rax, [rsp+48h+TokenInformationLength]
0x180005895  mov     r8, rbx; TokenInformation
0x180005898  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000589d  mov     edx, 1; TokenInformationClass
0x1800058a2  mov     rcx, rbp; TokenHandle
0x1800058a5  call    cs:__imp_GetTokenInformation
0x1800058ac  nop     dword ptr [rax+rax+00h]
0x1800058b1  mov     ecx, eax; int
0x1800058b3  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800058b8  mov     edi, eax
0x1800058ba  jmp     loc_180005739
0x1800058bf  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800058c4  mov     edi, eax
0x1800058c6  test    eax, eax
0x1800058c8  jns     loc_1800057A1
0x1800058ce  mov     rcx, rbp; lpMem
0x1800058d1  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x1800058d6  jmp     loc_1800057A4
0x1800058db  mov     edi, 8007000Eh
0x1800058e0  jmp     loc_1800057A4
0x1800058e5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800058ea  jmp     loc_1800057D1
0x1800058ef  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800058f4  jmp     loc_18000582D
```
