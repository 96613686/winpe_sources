# CHardwareManager::PublishFrameworkNotification(ulong,uint,_WINBIO_SERVER_MESSAGE &)

- ea: `0x180010a98`
- end: `0x180010bf3`
- name: `?PublishFrameworkNotification@CHardwareManager@@SAXKIAEAU_WINBIO_SERVER_MESSAGE@@@Z`
- size: `347`
- prototype: `static void(unsigned int, unsigned int, struct _WINBIO_SERVER_MESSAGE *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180010a3c`
- `0x18003e68c`

## callees

- `0x180010a98`
- `0x180010f18`
- `0x180011008`
- `0x180011044`
- `0x1800110f0`
- `0x180011128`
- `0x180011164`
- `0x1800119c4`
- `0x180058f24`
- `0x180068f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010bd1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010bd1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010acf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010acf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010b15`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010b15`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180010b9d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180010b9d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CHardwareManager::PublishFrameworkNotification(int a1, int a2, struct _WINBIO_SERVER_MESSAGE *a3)
{
  RTL_SRWLOCK *v6; // rdi
  RTL_SRWLOCK *v7; // rbx
  HANDLE *Ptr; // rcx
  unsigned int v9; // edx
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-99h] BYREF
  RTL_SRWLOCK *v11; // [rsp+38h] [rbp-91h] BYREF
  HANDLE hFile; // [rsp+40h] [rbp-89h] BYREF
  _QWORD v13[8]; // [rsp+50h] [rbp-79h] BYREF
  PTP_TIMER pv; // [rsp+90h] [rbp-39h] BYREF
  char v15; // [rsp+98h] [rbp-31h]
  char v16[64]; // [rsp+A0h] [rbp-29h] BYREF

  v6 = (RTL_SRWLOCK *)((char *)CHardwareManager::Instance() + 8);
  AcquireSRWLockExclusive(v6);
  v11 = v6;
  v7 = (RTL_SRWLOCK *)**((_QWORD **)CHardwareManager::Instance() + 9);
  v11 = v7;
  while ( !BYTE1(v7[3].Ptr) )
  {
    Ptr = (HANDLE *)v7[5].Ptr;
    if ( (a1 & (_DWORD)Ptr[2]) != 0 && ((a2 & *((_DWORD *)Ptr + 5)) != 0 || !*((_DWORD *)Ptr + 5)) )
    {
      SetEvent(*Ptr);
      hFile = (HANDLE)*((_QWORD *)v7[5].Ptr + 1);
      winbio::watchdog::watchdog(&pv);
      winbio::watchdog::Stop(&pv);
      v15 = 0;
      v13[0] = off_1800D3078;
      v13[1] = &hFile;
      v13[7] = v13;
      std::_Func_class<void,>::_Swap(v13, v16);
      std::_Func_class<void,>::_Tidy(v13);
      winbio::watchdog::Start((winbio::watchdog *)&pv, v9);
      NumberOfBytesWritten = 0;
      WriteFile(hFile, a3, 0x14u, &NumberOfBytesWritten, 0);
      winbio::watchdog::Stop(&pv);
      winbio::watchdog::~watchdog((winbio::watchdog *)&pv);
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_RPC_ASYNC_STATE * const,std::shared_ptr<CAsyncWorkItem>>>>,std::_Iterator_base0>::operator++(&v11);
    v7 = v11;
  }
  if ( v6 )
    ReleaseSRWLockExclusive(v6);
}

```

## disassembly

```asm
0x180010a98  push    rbp
0x180010a9a  push    rbx
0x180010a9b  push    rsi
0x180010a9c  push    rdi
0x180010a9d  push    r14
0x180010a9f  push    r15
0x180010aa1  lea     rbp, [rsp-2Fh]
0x180010aa6  sub     rsp, 0F8h
0x180010aad  mov     rax, cs:__security_cookie
0x180010ab4  xor     rax, rsp
0x180010ab7  mov     [rbp+57h+var_40], rax
0x180010abb  mov     r15, r8
0x180010abe  mov     esi, edx
0x180010ac0  mov     r14d, ecx
0x180010ac3  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180010ac8  lea     rdi, [rax+8]
0x180010acc  mov     rcx, rdi; SRWLock
0x180010acf  call    cs:__imp_AcquireSRWLockExclusive
0x180010ad5  mov     [rsp+120h+var_E8], rdi
0x180010ada  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180010adf  mov     rbx, [rax+48h]
0x180010ae3  mov     rbx, [rbx]
0x180010ae6  mov     [rsp+120h+var_E8], rbx
0x180010aeb  cmp     byte ptr [rbx+19h], 0
0x180010aef  jnz     loc_180010BC9
0x180010af5  mov     rcx, [rbx+28h]
0x180010af9  test    [rcx+10h], r14d
0x180010afd  jz      loc_180010BB5
0x180010b03  test    [rcx+14h], esi
0x180010b06  jnz     short loc_180010B12
0x180010b08  cmp     dword ptr [rcx+14h], 0
0x180010b0c  jnz     loc_180010BB5
0x180010b12  mov     rcx, [rcx]; hEvent
0x180010b15  call    cs:__imp_SetEvent
0x180010b1b  mov     rax, [rbx+28h]
0x180010b1f  mov     rcx, [rax+8]
0x180010b23  mov     [rsp+120h+hFile], rcx
0x180010b28  lea     rcx, [rbp+57h+pv]; pv
0x180010b2c  call    ??0watchdog@winbio@@QEAA@XZ; winbio::watchdog::watchdog(void)
0x180010b31  lea     rcx, [rbp+57h+pv]; this
0x180010b35  call    ?Stop@watchdog@winbio@@QEAAXXZ; winbio::watchdog::Stop(void)
0x180010b3a  mov     [rbp+57h+var_88], 0
0x180010b3e  lea     rax, off_1800D3078
0x180010b45  mov     [rbp+57h+var_D0], rax
0x180010b49  lea     rax, [rsp+120h+hFile]
0x180010b4e  mov     [rbp+57h+var_C8], rax
0x180010b52  lea     rax, [rbp+57h+var_D0]
0x180010b56  mov     [rbp+57h+var_98], rax
0x180010b5a  lea     rdx, [rbp+57h+var_80]
0x180010b5e  lea     rcx, [rbp+57h+var_D0]
0x180010b62  call    ?_Swap@?$_Func_class@X$$V@std@@IEAAXAEAV12@@Z; std::_Func_class<void,>::_Swap(std::_Func_class<void,> &)
0x180010b67  lea     rcx, [rbp+57h+var_D0]
0x180010b6b  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x180010b70  lea     rcx, [rbp+57h+pv]; this
0x180010b74  call    ?Start@watchdog@winbio@@QEAAXK@Z; winbio::watchdog::Start(ulong)
0x180010b79  mov     [rsp+120h+NumberOfBytesWritten], 0
0x180010b81  mov     [rsp+120h+lpOverlapped], 0; lpOverlapped
0x180010b8a  lea     r9, [rsp+120h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180010b8f  mov     r8d, 14h; nNumberOfBytesToWrite
0x180010b95  mov     rdx, r15; lpBuffer
0x180010b98  mov     rcx, [rsp+120h+hFile]; hFile
0x180010b9d  call    cs:__imp_WriteFile
0x180010ba3  lea     rcx, [rbp+57h+pv]; this
0x180010ba7  call    ?Stop@watchdog@winbio@@QEAAXXZ; winbio::watchdog::Stop(void)
0x180010bac  lea     rcx, [rbp+57h+pv]; this
0x180010bb0  call    ??1watchdog@winbio@@QEAA@XZ; winbio::watchdog::~watchdog(void)
0x180010bb5  lea     rcx, [rsp+120h+var_E8]
0x180010bba  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$shared_ptr@VCAsyncWorkItem@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_RPC_ASYNC_STATE * const,std::shared_ptr<CAsyncWorkItem>>>>,std::_Iterator_base0>::operator++(void)
0x180010bbf  mov     rbx, [rsp+120h+var_E8]
0x180010bc4  jmp     loc_180010AEB
0x180010bc9  test    rdi, rdi
0x180010bcc  jz      short loc_180010BD7
0x180010bce  mov     rcx, rdi; SRWLock
0x180010bd1  call    cs:__imp_ReleaseSRWLockExclusive
0x180010bd7  mov     rcx, [rbp+57h+var_40]
0x180010bdb  xor     rcx, rsp; StackCookie
0x180010bde  call    __security_check_cookie
0x180010be3  add     rsp, 0F8h
0x180010bea  pop     r15
0x180010bec  pop     r14
0x180010bee  pop     rdi
0x180010bef  pop     rsi
0x180010bf0  pop     rbx
0x180010bf1  pop     rbp
0x180010bf2  retn
```
