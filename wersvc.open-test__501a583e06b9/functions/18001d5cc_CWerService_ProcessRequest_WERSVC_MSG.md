# CWerService::_ProcessRequest(_WERSVC_MSG *)

- ea: `0x18001d5cc`
- end: `0x18001d7ba`
- name: `?_ProcessRequest@CWerService@@AEAAJPEAU_WERSVC_MSG@@@Z`
- size: `494`
- prototype: `__int64 __fastcall(CWerService *__hidden this, struct _WERSVC_MSG *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x180015d18`
- `0x18001d380`

## callees

- `0x1800029f4`
- `0x180002a00`
- `0x1800035e8`
- `0x180006a80`
- `0x180011ef8`
- `0x180014c54`
- `0x18001d5cc`
- `0x18001e3c4`
- `0x180034550`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d74c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d74c`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18001d737`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18001d737`

## pseudocode

```c
__int64 __fastcall CWerService::_ProcessRequest(CWerService *this, struct _WERSVC_MSG *a2)
{
  signed int v4; // ebx
  _QWORD *v6; // rax
  _QWORD *v7; // r14
  signed int LastError; // eax
  _BYTE Src[1464]; // [rsp+30h] [rbp-5B8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_DDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      82,
      WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
      *((unsigned int *)a2 + 2),
      *((_DWORD *)a2 + 4),
      *((_DWORD *)a2 + 10));
  v4 = CWerService::CheckIfValidPortMessage(this, a2);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
    return (unsigned int)v4;
  }
  if ( *((_DWORD *)a2 + 10) == 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
    return 0;
  }
  else if ( (*((_BYTE *)this + 212) & 1) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
    return 2147943515LL;
  }
  else
  {
    v6 = operator new(0x580u, (const struct std::nothrow_t *)&std::nothrow);
    v7 = v6;
    if ( v6 )
    {
      memset_0(v6 + 1, 0, 0x578u);
      *v7 = this;
      memcpy_0(Src, a2, 0x578u);
      memcpy_0(v7 + 1, Src, 0x578u);
      _InterlockedIncrement((volatile signed __int32 *)this + 52);
      if ( !TrySubmitThreadpoolCallback(
              CWerService::StaticDispatchPortRequestWorkItem,
              v7,
              (PTP_CALLBACK_ENVIRON)((char *)this + 232)) )
      {
        _InterlockedDecrement((volatile signed __int32 *)this + 52);
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        if ( v4 >= 0 )
          v4 = -2147467259;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            86,
            WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
            (unsigned int)v4);
        operator delete(v7, (const struct std::nothrow_t *)0x580);
      }
      return (unsigned int)v4;
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18001d5cc  push    rbx
0x18001d5ce  push    rbp
0x18001d5cf  push    rsi
0x18001d5d0  push    rdi
0x18001d5d1  push    r12
0x18001d5d3  push    r14
0x18001d5d5  push    r15
0x18001d5d7  sub     rsp, 5B0h
0x18001d5de  mov     rdi, rdx
0x18001d5e1  mov     rsi, rcx
0x18001d5e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d5eb  lea     r15, WPP_GLOBAL_Control
0x18001d5f2  lea     r12, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001d5f9  mov     bpl, 4
0x18001d5fc  cmp     rcx, r15
0x18001d5ff  jz      short loc_18001D62A
0x18001d601  test    [rcx+1Ch], bpl
0x18001d605  jz      short loc_18001D62A
0x18001d607  mov     eax, [rdi+28h]
0x18001d60a  mov     edx, 52h ; 'R'
0x18001d60f  mov     r9d, [rdi+8]
0x18001d613  mov     r8, r12
0x18001d616  mov     rcx, [rcx+10h]
0x18001d61a  mov     [rsp+5E8h+var_5C0], eax
0x18001d61e  mov     eax, [rdi+10h]
0x18001d621  mov     [rsp+5E8h+var_5C8], eax
0x18001d625  call    WPP_SF_DDD
0x18001d62a  mov     rdx, rdi; struct _WERSVC_MSG *
0x18001d62d  mov     rcx, rsi; this
0x18001d630  call    ?CheckIfValidPortMessage@CWerService@@AEAAJPEAU_WERSVC_MSG@@@Z; CWerService::CheckIfValidPortMessage(_WERSVC_MSG *)
0x18001d635  mov     ebx, eax
0x18001d637  test    eax, eax
0x18001d639  jns     short loc_18001D665
0x18001d63b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d642  cmp     rcx, r15
0x18001d645  jz      short loc_18001D65E
0x18001d647  test    byte ptr [rcx+1Ch], 2
0x18001d64b  jz      short loc_18001D65E
0x18001d64d  mov     rcx, [rcx+10h]
0x18001d651  mov     edx, 53h ; 'S'
0x18001d656  mov     r8, r12
0x18001d659  call    WPP_SF_
0x18001d65e  mov     eax, ebx
0x18001d660  jmp     loc_18001D7A8
0x18001d665  cmp     dword ptr [rdi+28h], 2
0x18001d669  jnz     short loc_18001D695
0x18001d66b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d672  cmp     rcx, r15
0x18001d675  jz      short loc_18001D68E
0x18001d677  test    [rcx+1Ch], bpl
0x18001d67b  jz      short loc_18001D68E
0x18001d67d  mov     rcx, [rcx+10h]
0x18001d681  mov     edx, 54h ; 'T'
0x18001d686  mov     r8, r12
0x18001d689  call    WPP_SF_
0x18001d68e  xor     eax, eax
0x18001d690  jmp     loc_18001D7A8
0x18001d695  test    byte ptr [rsi+0D4h], 1
0x18001d69c  jz      short loc_18001D6CB
0x18001d69e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d6a5  cmp     rcx, r15
0x18001d6a8  jz      short loc_18001D6C1
0x18001d6aa  test    [rcx+1Ch], bpl
0x18001d6ae  jz      short loc_18001D6C1
0x18001d6b0  mov     rcx, [rcx+10h]
0x18001d6b4  mov     edx, 55h ; 'U'
0x18001d6b9  mov     r8, r12
0x18001d6bc  call    WPP_SF_
0x18001d6c1  mov     eax, 8007045Bh
0x18001d6c6  jmp     loc_18001D7A8
0x18001d6cb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d6d2  mov     ecx, 580h; unsigned __int64
0x18001d6d7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001d6dc  mov     r14, rax
0x18001d6df  test    rax, rax
0x18001d6e2  jz      loc_18001D7A3
0x18001d6e8  mov     ebp, 578h
0x18001d6ed  lea     rcx, [rax+8]; void *
0x18001d6f1  mov     r8d, ebp; Size
0x18001d6f4  xor     edx, edx; Val
0x18001d6f6  call    memset_0
0x18001d6fb  lea     rcx, [rsp+5E8h+Src]; void *
0x18001d700  mov     [r14], rsi
0x18001d703  mov     rdx, rdi; Src
0x18001d706  mov     r8d, ebp; Size
0x18001d709  call    memcpy_0
0x18001d70e  lea     rcx, [r14+8]; void *
0x18001d712  mov     r8d, ebp; Size
0x18001d715  lea     rdx, [rsp+5E8h+Src]; Src
0x18001d71a  call    memcpy_0
0x18001d71f  lock inc dword ptr [rsi+0D0h]
0x18001d726  lea     r8, [rsi+0E8h]; pcbe
0x18001d72d  mov     rdx, r14; pv
0x18001d730  lea     rcx, ?StaticDispatchPortRequestWorkItem@CWerService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18001d737  call    cs:__imp_TrySubmitThreadpoolCallback
0x18001d73d  test    eax, eax
0x18001d73f  jnz     loc_18001D65E
0x18001d745  lock dec dword ptr [rsi+0D0h]
0x18001d74c  call    cs:__imp_GetLastError
0x18001d752  mov     ebx, eax
0x18001d754  test    eax, eax
0x18001d756  jle     short loc_18001D761
0x18001d758  movzx   ebx, ax
0x18001d75b  or      ebx, 80070000h
0x18001d761  test    ebx, ebx
0x18001d763  mov     eax, 80004005h
0x18001d768  cmovns  ebx, eax
0x18001d76b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d772  cmp     rcx, r15
0x18001d775  jz      short loc_18001D791
0x18001d777  test    byte ptr [rcx+1Ch], 1
0x18001d77b  jz      short loc_18001D791
0x18001d77d  mov     rcx, [rcx+10h]
0x18001d781  mov     edx, 56h ; 'V'
0x18001d786  mov     r9d, ebx
0x18001d789  mov     r8, r12
0x18001d78c  call    WPP_SF_d
0x18001d791  mov     edx, 580h; struct std::nothrow_t *
0x18001d796  mov     rcx, r14; void *
0x18001d799  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001d79e  jmp     loc_18001D65E
0x18001d7a3  mov     eax, 8007000Eh
0x18001d7a8  add     rsp, 5B0h
0x18001d7af  pop     r15
0x18001d7b1  pop     r14
0x18001d7b3  pop     r12
0x18001d7b5  pop     rdi
0x18001d7b6  pop     rsi
0x18001d7b7  pop     rbp
0x18001d7b8  pop     rbx
0x18001d7b9  retn
```
