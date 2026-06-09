# TCProducerConsumer<CSBESampleWrapper *>::Pop(CSBESampleWrapper * *)

- ea: `0x180016aa4`
- end: `0x180016c0b`
- name: `?Pop@?$TCProducerConsumer@PEAVCSBESampleWrapper@@@@QEAAKPEAPEAVCSBESampleWrapper@@@Z`
- size: `359`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180014390`
- `0x180059504`

## callees

- `0x1800017a0`
- `0x1800017e0`
- `0x180013500`
- `0x180013548`
- `0x180016aa4`
- `0x1800177c8`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180016b73`
- `KERNEL32!WaitForSingleObject` at `0x180016b73`
- `KERNEL32!ResetEvent` at `0x180016b38`
- `KERNEL32!ResetEvent` at `0x180016b38`
- `KERNEL32!CreateEventW` at `0x180016b0c`
- `KERNEL32!CreateEventW` at `0x180016b0c`
- `KERNEL32!LeaveCriticalSection` at `0x180016b67`
- `KERNEL32!LeaveCriticalSection` at `0x180016bf6`
- `KERNEL32!LeaveCriticalSection` at `0x180016b67`
- `KERNEL32!LeaveCriticalSection` at `0x180016bf6`
- `KERNEL32!EnterCriticalSection` at `0x180016abe`
- `KERNEL32!EnterCriticalSection` at `0x180016b80`
- `KERNEL32!EnterCriticalSection` at `0x180016b9b`
- `KERNEL32!EnterCriticalSection` at `0x180016abe`
- `KERNEL32!EnterCriticalSection` at `0x180016b80`
- `KERNEL32!EnterCriticalSection` at `0x180016b9b`

## pseudocode

```c
__int64 __fastcall TCProducerConsumer<CSBESampleWrapper *>::Pop(LPCRITICAL_SECTION lpCriticalSection, _QWORD *a2)
{
  _QWORD *v4; // rax
  HANDLE *v5; // rax
  HANDLE *v6; // rsi
  HANDLE EventW; // rax
  unsigned int v8; // edi
  LPCRITICAL_SECTION *OwningThread; // rcx
  LPCRITICAL_SECTION **v10; // r14
  HANDLE *p_OwningThread; // rax
  LPCRITICAL_SECTION *v12; // rcx

  *a2 = 0;
  EnterCriticalSection(lpCriticalSection);
  v4 = (_QWORD *)TCProducerConsumer<CPooledWMINSSBuffer3Wrapper *>::ContainerAvailPop_(lpCriticalSection);
  if ( v4 )
  {
    *a2 = *v4;
    TCProducerConsumer<CPooledMediaSampleWrapper *>::ContainerPoolPush_(lpCriticalSection, v4);
    v8 = 0;
    goto LABEL_21;
  }
  if ( !LODWORD(lpCriticalSection[2].LockSemaphore) )
    goto LABEL_8;
  v5 = (HANDLE *)TCProducerConsumer<CDVRAttribute *>::RequestPoolPop_(lpCriticalSection, 0);
  v6 = v5;
  if ( v5 )
  {
    ResetEvent(*v5);
  }
  else
  {
    v6 = (HANDLE *)operator new(0x28u);
    if ( v6 )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      *v6 = EventW;
      if ( !EventW )
      {
        operator delete(v6, 0x28u);
        v6 = 0;
      }
    }
    if ( !v6 )
    {
LABEL_8:
      v8 = 31;
      goto LABEL_21;
    }
  }
  OwningThread = (LPCRITICAL_SECTION *)lpCriticalSection[2].OwningThread;
  if ( *OwningThread != (LPCRITICAL_SECTION)&lpCriticalSection[2].LockCount )
    goto LABEL_19;
  v10 = (LPCRITICAL_SECTION **)(v6 + 3);
  v6[4] = OwningThread;
  v6[3] = &lpCriticalSection[2].LockCount;
  *OwningThread = (LPCRITICAL_SECTION)(v6 + 3);
  lpCriticalSection[2].OwningThread = v6 + 3;
  ++HIDWORD(lpCriticalSection[2].LockSemaphore);
  LeaveCriticalSection(lpCriticalSection);
  if ( WaitForSingleObject(*v6, 0xFFFFFFFF) )
  {
    v8 = 31;
    EnterCriticalSection(lpCriticalSection);
  }
  else
  {
    EnterCriticalSection(lpCriticalSection);
    v8 = *((_DWORD *)v6 + 2);
    if ( !v8 )
      *a2 = v6[2];
  }
  if ( lpCriticalSection[3].LockCount >= SHIDWORD(lpCriticalSection[3].DebugInfo) )
  {
    operator delete(v6, 0x28u);
    goto LABEL_21;
  }
  p_OwningThread = &lpCriticalSection[1].OwningThread;
  v12 = (LPCRITICAL_SECTION *)lpCriticalSection[1].OwningThread;
  if ( v12[1] != (LPCRITICAL_SECTION)&lpCriticalSection[1].OwningThread )
LABEL_19:
    __fastfail(3u);
  *v10 = v12;
  v6[4] = p_OwningThread;
  v12[1] = (LPCRITICAL_SECTION)v10;
  *p_OwningThread = v10;
  ++lpCriticalSection[3].LockCount;
LABEL_21:
  LeaveCriticalSection(lpCriticalSection);
  return v8;
}

```

## disassembly

```asm
0x180016aa4  push    rbx
0x180016aa6  push    rbp
0x180016aa7  push    rsi
0x180016aa8  push    rdi
0x180016aa9  push    r14
0x180016aab  push    r15
0x180016aad  sub     rsp, 28h
0x180016ab1  mov     r15, rdx
0x180016ab4  mov     qword ptr [rdx], 0
0x180016abb  mov     rbx, rcx
0x180016abe  call    cs:__imp_EnterCriticalSection
0x180016ac4  mov     rcx, rbx
0x180016ac7  call    ?ContainerAvailPop_@?$TCProducerConsumer@PEAVCPooledWMINSSBuffer3Wrapper@@@@AEAAPEAUOBJ_CONTAINER@1@XZ; TCProducerConsumer<CPooledWMINSSBuffer3Wrapper *>::ContainerAvailPop_(void)
0x180016acc  mov     rdx, rax
0x180016acf  test    rax, rax
0x180016ad2  jnz     loc_180016BE3
0x180016ad8  cmp     [rbx+68h], eax
0x180016adb  jz      short loc_180016B2B
0x180016add  mov     rcx, rbx
0x180016ae0  call    ?RequestPoolPop_@?$TCProducerConsumer@PEAVCDVRAttribute@@@@AEAAPEAUOBJ_REQUEST@1@XZ; TCProducerConsumer<CDVRAttribute *>::RequestPoolPop_(void)
0x180016ae5  mov     rsi, rax
0x180016ae8  mov     ebp, 28h ; '('
0x180016aed  test    rax, rax
0x180016af0  jnz     short loc_180016B35
0x180016af2  mov     ecx, ebp; Size
0x180016af4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016af9  mov     rsi, rax
0x180016afc  test    rax, rax
0x180016aff  jz      short loc_180016B26
0x180016b01  xor     r9d, r9d; lpName
0x180016b04  lea     edx, [rbp-27h]; bManualReset
0x180016b07  xor     r8d, r8d; bInitialState
0x180016b0a  xor     ecx, ecx; lpEventAttributes
0x180016b0c  call    cs:__imp_CreateEventW
0x180016b12  mov     [rsi], rax
0x180016b15  test    rax, rax
0x180016b18  jnz     short loc_180016B26
0x180016b1a  mov     edx, ebp; unsigned __int64
0x180016b1c  mov     rcx, rsi; void *
0x180016b1f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016b24  xor     esi, esi
0x180016b26  test    rsi, rsi
0x180016b29  jnz     short loc_180016B3E
0x180016b2b  mov     edi, 1Fh
0x180016b30  jmp     loc_180016BF3
0x180016b35  mov     rcx, [rax]; hEvent
0x180016b38  call    cs:__imp_ResetEvent
0x180016b3e  lea     rax, [rbx+58h]
0x180016b42  mov     rcx, [rax+8]
0x180016b46  cmp     [rcx], rax
0x180016b49  jnz     loc_180016BDC
0x180016b4f  lea     r14, [rsi+18h]
0x180016b53  mov     [r14+8], rcx
0x180016b57  mov     [r14], rax
0x180016b5a  mov     [rcx], r14
0x180016b5d  mov     rcx, rbx; lpCriticalSection
0x180016b60  mov     [rax+8], r14
0x180016b64  inc     dword ptr [rbx+6Ch]
0x180016b67  call    cs:__imp_LeaveCriticalSection
0x180016b6d  mov     rcx, [rsi]; hHandle
0x180016b70  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180016b73  call    cs:__imp_WaitForSingleObject
0x180016b79  mov     rcx, rbx; lpCriticalSection
0x180016b7c  test    eax, eax
0x180016b7e  jnz     short loc_180016B96
0x180016b80  call    cs:__imp_EnterCriticalSection
0x180016b86  mov     edi, [rsi+8]
0x180016b89  test    edi, edi
0x180016b8b  jnz     short loc_180016BA1
0x180016b8d  mov     rax, [rsi+10h]
0x180016b91  mov     [r15], rax
0x180016b94  jmp     short loc_180016BA1
0x180016b96  mov     edi, 1Fh
0x180016b9b  call    cs:__imp_EnterCriticalSection
0x180016ba1  mov     eax, [rbx+7Ch]
0x180016ba4  cmp     [rbx+80h], eax
0x180016baa  jge     short loc_180016BCF
0x180016bac  lea     rax, [rbx+38h]
0x180016bb0  mov     rcx, [rax]
0x180016bb3  cmp     [rcx+8], rax
0x180016bb7  jnz     short loc_180016BDC
0x180016bb9  mov     [r14], rcx
0x180016bbc  mov     [r14+8], rax
0x180016bc0  mov     [rcx+8], r14
0x180016bc4  mov     [rax], r14
0x180016bc7  inc     dword ptr [rbx+80h]
0x180016bcd  jmp     short loc_180016BF3
0x180016bcf  mov     rdx, rbp; unsigned __int64
0x180016bd2  mov     rcx, rsi; void *
0x180016bd5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016bda  jmp     short loc_180016BF3
0x180016bdc  mov     ecx, 3
0x180016be1  int     29h; Win8: RtlFailFast(ecx)
0x180016be3  mov     rax, [rax]
0x180016be6  mov     rcx, rbx
0x180016be9  mov     [r15], rax
0x180016bec  call    ?ContainerPoolPush_@?$TCProducerConsumer@PEAVCPooledMediaSampleWrapper@@@@AEAAXPEAUOBJ_CONTAINER@1@@Z; TCProducerConsumer<CPooledMediaSampleWrapper *>::ContainerPoolPush_(TCProducerConsumer<CPooledMediaSampleWrapper *>::OBJ_CONTAINER *)
0x180016bf1  xor     edi, edi
0x180016bf3  mov     rcx, rbx; lpCriticalSection
0x180016bf6  call    cs:__imp_LeaveCriticalSection
0x180016bfc  mov     eax, edi
0x180016bfe  add     rsp, 28h
0x180016c02  pop     r15
0x180016c04  pop     r14
0x180016c06  pop     rdi
0x180016c07  pop     rsi
0x180016c08  pop     rbp
0x180016c09  pop     rbx
0x180016c0a  retn
```
