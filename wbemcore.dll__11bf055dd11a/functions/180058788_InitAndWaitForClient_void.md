# InitAndWaitForClient(void)

- ea: `0x180058788`
- end: `0x1800589e9`
- name: `?InitAndWaitForClient@@YAJXZ`
- size: `609`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180062150`
- `0x1800ac040`
- `0x1800ac170`

## callees

- `0x18000b140`
- `0x18000b46c`
- `0x180058788`
- `0x1800589f0`
- `0x180058ab0`
- `0x180059114`
- `0x180063bd8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180058992`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180058992`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800587ee`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800587ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800589d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800589d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800588fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800588fc`
- `wbemcomn!?SetLogingEnabled@CMemoryLog@@QEAAX_N@Z` at `0x180058935`
- `wbemcomn!?SetLogingEnabled@CMemoryLog@@QEAAX_N@Z` at `0x180058935`
- `wbemcomn!GetMemLogObject` at `0x180058864`
- `wbemcomn!GetMemLogObject` at `0x1800588a1`
- `wbemcomn!GetMemLogObject` at `0x180058914`
- `wbemcomn!GetMemLogObject` at `0x18005892a`
- `wbemcomn!GetMemLogObject` at `0x180058944`
- `wbemcomn!GetMemLogObject` at `0x180058864`
- `wbemcomn!GetMemLogObject` at `0x1800588a1`
- `wbemcomn!GetMemLogObject` at `0x180058914`
- `wbemcomn!GetMemLogObject` at `0x18005892a`
- `wbemcomn!GetMemLogObject` at `0x180058944`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180058870`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800588ac`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005891f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005894f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180058870`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800588ac`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005891f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005894f`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x180058812`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x180058812`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 InitAndWaitForClient(void)
{
  int v0; // ebx
  CClientCnt *v1; // rcx
  CMemoryLog *MemLogObject; // rax
  __int64 v4; // rdx
  CMemoryLog *v5; // rax
  signed int LastError; // eax
  CMemoryLog *v7; // rax
  CMemoryLog *v8; // rax
  CMemoryLog *v9; // rax
  IUnknown *pNewObject[2]; // [rsp+20h] [rbp-18h] BYREF
  IUnknown *ppOldObject; // [rsp+60h] [rbp+28h] BYREF

  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids);
  }
  *(_OWORD *)pNewObject = 0;
  v0 = CThreadInfo::Initialize(pNewObject);
  if ( v0 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v0);
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = 11;
LABEL_36:
      WPP_SF_d(*((_QWORD *)v1 + 2), v4, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids, (unsigned int)v0);
    }
LABEL_10:
    pNewObject[0] = 0;
    if ( pNewObject[1] )
    {
      CloseHandle(pNewObject[1]);
      pNewObject[1] = 0;
    }
    return (unsigned int)v0;
  }
  v0 = EnsureInitialized();
  if ( v0 >= 0 )
  {
    WaitForSingleObject(g_hOpenForClients, 0xFFFFFFFF);
    v0 = g_hresForClients;
    if ( g_hresForClients >= 0 )
    {
      ppOldObject = 0;
      CoSwitchCallContext(pNewObject[0], &ppOldObject);
      if ( (unsigned __int64)&pNewObject[1][-1].lpVtbl + 7 > 0xFFFFFFFFFFFFFFFDuLL || SetThreadToken(0, pNewObject[1]) )
      {
        v0 = 0;
      }
      else
      {
        LastError = GetLastError();
        v0 = LastError;
        if ( LastError > 0 )
          v0 = (unsigned __int16)LastError | 0x80070000;
        if ( v0 < 0 )
        {
          v7 = GetMemLogObject();
          CMemoryLog::Write(v7, v0);
        }
      }
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_10;
      }
      v4 = 14;
      goto LABEL_36;
    }
    CThreadInfo::Finalize(pNewObject);
    v5 = GetMemLogObject();
    CMemoryLog::Write(v5, v0);
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = 13;
      goto LABEL_36;
    }
    goto LABEL_10;
  }
  v8 = GetMemLogObject();
  CMemoryLog::SetLogingEnabled(v8, 0);
  CThreadInfo::Finalize(pNewObject);
  v9 = GetMemLogObject();
  CMemoryLog::Write(v9, v0);
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids, (unsigned int)v0);
  }
  CThreadInfo::~CThreadInfo((CThreadInfo *)pNewObject);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180058788  push    rbp
0x18005878a  push    rbx
0x18005878b  push    r14
0x18005878d  push    r15
0x18005878f  mov     rbp, rsp
0x180058792  sub     rsp, 38h
0x180058796  lea     r15, WPP_GLOBAL_Control
0x18005879d  lea     r14, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids
0x1800587a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800587ab  cmp     rcx, r15
0x1800587ae  jz      short loc_1800587BA
0x1800587b0  test    byte ptr [rcx+1Ch], 1
0x1800587b4  jnz     loc_1800588DC
0x1800587ba  xorps   xmm0, xmm0
0x1800587bd  movdqu  xmmword ptr [rbp+pNewObject], xmm0
0x1800587c2  lea     rcx, [rbp+pNewObject]; ppOldObject
0x1800587c6  call    ?Initialize@CThreadInfo@@QEAAJXZ; CThreadInfo::Initialize(void)
0x1800587cb  mov     ebx, eax
0x1800587cd  test    eax, eax
0x1800587cf  js      loc_180058864
0x1800587d5  call    ?EnsureInitialized@@YAJXZ; EnsureInitialized(void)
0x1800587da  mov     ebx, eax
0x1800587dc  test    eax, eax
0x1800587de  js      loc_18005892A
0x1800587e4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800587e7  mov     rcx, cs:?g_hOpenForClients@@3PEAXEA; hHandle
0x1800587ee  call    cs:__imp_WaitForSingleObject
0x1800587f4  mov     ebx, cs:?g_hresForClients@@3JA; long g_hresForClients
0x1800587fa  test    ebx, ebx
0x1800587fc  js      loc_180058898
0x180058802  mov     [rbp+ppOldObject], 0
0x18005880a  lea     rdx, [rbp+ppOldObject]; ppOldObject
0x18005880e  mov     rcx, [rbp+pNewObject]; pNewObject
0x180058812  call    cs:__imp_CoSwitchCallContext
0x180058818  mov     rdx, [rbp+pNewObject+8]; Token
0x18005881c  lea     rax, [rdx-1]
0x180058820  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180058824  jbe     loc_180058990
0x18005882a  xor     ebx, ebx
0x18005882c  mov     rcx, cs:WPP_GLOBAL_Control
0x180058833  cmp     rcx, r15
0x180058836  jz      short loc_180058842
0x180058838  test    byte ptr [rcx+1Ch], 1
0x18005883c  jnz     loc_1800589B3
0x180058842  mov     rcx, [rbp+pNewObject+8]; hObject
0x180058846  mov     [rbp+pNewObject], 0
0x18005884e  test    rcx, rcx
0x180058851  jnz     loc_1800589D6
0x180058857  mov     eax, ebx
0x180058859  add     rsp, 38h
0x18005885d  pop     r15
0x18005885f  pop     r14
0x180058861  pop     rbx
0x180058862  pop     rbp
0x180058863  retn
0x180058864  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005886a  nop
0x18005886b  mov     edx, ebx
0x18005886d  mov     rcx, rax
0x180058870  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180058876  mov     rcx, cs:WPP_GLOBAL_Control
0x18005887d  cmp     rcx, r15
0x180058880  jz      short loc_180058842
0x180058882  test    byte ptr [rcx+1Ch], 1
0x180058886  jz      short loc_180058842
0x180058888  cmp     byte ptr [rcx+19h], 2
0x18005888c  jb      short loc_180058842
0x18005888e  mov     edx, 0Bh
0x180058893  jmp     loc_1800589C2
0x180058898  lea     rcx, [rbp+pNewObject]; this
0x18005889c  call    ?Finalize@CThreadInfo@@QEAAJXZ; CThreadInfo::Finalize(void)
0x1800588a1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800588a7  mov     edx, ebx
0x1800588a9  mov     rcx, rax
0x1800588ac  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800588b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800588b9  cmp     rcx, r15
0x1800588bc  jz      short loc_180058842
0x1800588be  test    byte ptr [rcx+1Ch], 1
0x1800588c2  jz      loc_180058842
0x1800588c8  cmp     byte ptr [rcx+19h], 2
0x1800588cc  jb      loc_180058842
0x1800588d2  mov     edx, 0Dh
0x1800588d7  jmp     loc_1800589C2
0x1800588dc  cmp     byte ptr [rcx+19h], 5
0x1800588e0  jb      loc_1800587BA
0x1800588e6  mov     edx, 0Ah
0x1800588eb  mov     r8, r14
0x1800588ee  mov     rcx, [rcx+10h]
0x1800588f2  call    WPP_SF_
0x1800588f7  jmp     loc_1800587BA
0x1800588fc  call    cs:__imp_GetLastError
0x180058902  mov     ebx, eax
0x180058904  test    eax, eax
0x180058906  jg      loc_1800589A5
0x18005890c  test    ebx, ebx
0x18005890e  jns     loc_18005882C
0x180058914  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005891a  mov     edx, ebx
0x18005891c  mov     rcx, rax
0x18005891f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180058925  jmp     loc_18005882C
0x18005892a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180058930  xor     edx, edx
0x180058932  mov     rcx, rax
0x180058935  call    cs:__imp_?SetLogingEnabled@CMemoryLog@@QEAAX_N@Z; CMemoryLog::SetLogingEnabled(bool)
0x18005893b  lea     rcx, [rbp+pNewObject]; this
0x18005893f  call    ?Finalize@CThreadInfo@@QEAAJXZ; CThreadInfo::Finalize(void)
0x180058944  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005894a  mov     edx, ebx
0x18005894c  mov     rcx, rax
0x18005894f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180058955  mov     rcx, cs:WPP_GLOBAL_Control
0x18005895c  cmp     rcx, r15
0x18005895f  jz      short loc_180058982
0x180058961  test    byte ptr [rcx+1Ch], 1
0x180058965  jz      short loc_180058982
0x180058967  cmp     byte ptr [rcx+19h], 2
0x18005896b  jb      short loc_180058982
0x18005896d  mov     edx, 0Ch
0x180058972  mov     r9d, ebx
0x180058975  mov     r8, r14
0x180058978  mov     rcx, [rcx+10h]
0x18005897c  call    WPP_SF_d
0x180058981  nop
0x180058982  lea     rcx, [rbp+pNewObject]; this
0x180058986  call    ??1CThreadInfo@@QEAA@XZ; CThreadInfo::~CThreadInfo(void)
0x18005898b  jmp     loc_180058857
0x180058990  xor     ecx, ecx; Thread
0x180058992  call    cs:__imp_SetThreadToken
0x180058998  test    eax, eax
0x18005899a  jnz     loc_18005882A
0x1800589a0  jmp     loc_1800588FC
0x1800589a5  movzx   ebx, ax
0x1800589a8  or      ebx, 80070000h
0x1800589ae  jmp     loc_18005890C
0x1800589b3  cmp     byte ptr [rcx+19h], 2
0x1800589b7  jb      loc_180058842
0x1800589bd  mov     edx, 0Eh
0x1800589c2  mov     r9d, ebx
0x1800589c5  mov     r8, r14
0x1800589c8  mov     rcx, [rcx+10h]
0x1800589cc  call    WPP_SF_d
0x1800589d1  jmp     loc_180058842
0x1800589d6  call    cs:__imp_CloseHandle
0x1800589dc  mov     [rbp+pNewObject+8], 0
0x1800589e4  jmp     loc_180058857
```
