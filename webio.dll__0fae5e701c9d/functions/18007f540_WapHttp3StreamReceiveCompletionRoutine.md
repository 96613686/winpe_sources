# WapHttp3StreamReceiveCompletionRoutine

- ea: `0x18007f540`
- end: `0x18007f860`
- name: `WapHttp3StreamReceiveCompletionRoutine`
- size: `800`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180079c10`

## callees

- `0x18005fd88`
- `0x1800722f0`
- `0x18007b1dc`
- `0x18007ec98`
- `0x18007edb8`
- `0x18007ee9c`
- `0x18007ef88`
- `0x18007f260`
- `0x18007f540`
- `0x18008033c`
- `0x180080830`
- `0x180093944`
- `0x1800971ec`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007f770`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007f770`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007f7c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007f7c6`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18007f6d5`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18007f6d5`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18007f689`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18007f689`

## pseudocode

```c
__int64 __fastcall WapHttp3StreamReceiveCompletionRoutine(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 v3; // rdi
  __int64 v7; // r8
  _QWORD *v8; // r14
  char v9; // al
  unsigned int Error; // esi
  __int64 v11; // rcx
  void (__fastcall *v12)(__int64, _QWORD, __int64); // rax
  __int64 result; // rax
  unsigned int v14; // [rsp+74h] [rbp-34h] BYREF

  v3 = *(_QWORD *)(a1 + 8);
  v14 = 0;
  WapHttp3StreamUpdateTimerOnCompletion(v3, v3 + 104);
  v8 = (_QWORD *)(v3 + 24);
  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
    WPP_SF_iD(1050, 227, v7, *v8, a2);
  v9 = BYTE1(Microsoft_Windows_WebIOEnableBits);
  if ( (Microsoft_Windows_WebIOEnableBits & 0x2000) != 0 )
  {
    McTemplateU0ppxppqxxxtt_EventWriteTransfer(
      a1 + 24,
      (unsigned int)NetSocketRecvEntityComplete,
      *(_QWORD *)(v3 + 8),
      0,
      0,
      *(_QWORD *)(a1 + 136),
      a1 + 24,
      a2,
      a3,
      *v8,
      *(_QWORD *)(a1 + 144),
      0,
      0);
    v9 = BYTE1(Microsoft_Windows_WebIOEnableBits);
  }
  if ( a2 != 234 )
    goto LABEL_15;
  if ( !*(_BYTE *)(a1 + 132) )
  {
    if ( (v9 & 0x20) != 0 )
      McTemplateU0ppxppqxxxtt_EventWriteTransfer(
        a1 + 24,
        (unsigned int)NetSocketRecvEntity,
        *(_QWORD *)(v3 + 8),
        0,
        0,
        *(_QWORD *)(a1 + 136),
        a1 + 24,
        0,
        0,
        *v8,
        *(_QWORD *)(a1 + 144),
        0,
        0);
    StartThreadpoolIo(*(PTP_IO *)(*(_QWORD *)(v3 + 40) + 8LL));
    a2 = WaHttpApiStreamReceiveEntityBody(
           **(_QWORD **)(v3 + 40),
           *(_QWORD *)(v3 + 24),
           1,
           *(_QWORD *)(a1 + 136),
           *(_DWORD *)(a1 + 144),
           0,
           (__int64)&v14);
    CancelThreadpoolIo(*(PTP_IO *)(*(_QWORD *)(v3 + 40) + 8LL));
    if ( (Microsoft_Windows_WebIOEnableBits & 0x2000) != 0 )
      McTemplateU0ppxppqxxxtt_EventWriteTransfer(
        *(_QWORD *)(v3 + 24),
        (unsigned int)NetSocketRecvEntityComplete,
        *(_QWORD *)(v3 + 8),
        0,
        0,
        *(_QWORD *)(a1 + 136),
        a1 + 24,
        a2,
        v14,
        *(_QWORD *)(v3 + 24),
        *(_QWORD *)(a1 + 144),
        0,
        0);
    if ( a2 == 234 || a2 == 997 )
    {
      if ( (BYTE3(xmmword_1800AD710) & 4) != 0 )
        WPP_SF_d(538, 228, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids, a2);
      goto LABEL_7;
    }
    a3 = v14;
LABEL_15:
    Error = WapHttp3StreamGetError(a2, v3);
    goto LABEL_16;
  }
LABEL_7:
  Error = 1359;
LABEL_16:
  EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 48));
  *(_QWORD *)(v3 + 304) = 0;
  WapHttp3StreamCheckForGoawayResend(v3, Error);
  WapHttp3StreamCheckForDowngrade(v3, Error);
  WapHttp3StreamCheckForTrailers(v3, a3, Error);
  WapHttp3StreamCheckForReset(v3, Error);
  if ( !Error && !a3 )
    *(_DWORD *)(v3 + 296) = 3;
  LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 48));
  *(_DWORD *)(a1 + 112) = Error;
  *(_QWORD *)(a1 + 120) = a3;
  if ( !*(_BYTE *)(a1 + 132) )
  {
    v11 = *(_QWORD *)(a1 + 104);
    v12 = *(void (__fastcall **)(__int64, _QWORD, __int64))(a1 + 96);
    *(_BYTE *)(a1 + 132) = 1;
    v12(v11, Error, a3);
  }
  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 4), 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
    return WapHttpApiFreeIoContext(a1);
  return result;
}

```

## disassembly

```asm
0x18007f540  mov     [rsp+arg_10], rbx
0x18007f545  push    rbp
0x18007f546  push    rsi
0x18007f547  push    rdi
0x18007f548  push    r14
0x18007f54a  push    r15
0x18007f54c  sub     rsp, 80h
0x18007f553  mov     rax, cs:__security_cookie
0x18007f55a  xor     rax, rsp
0x18007f55d  mov     [rsp+0A8h+var_30], rax
0x18007f562  mov     rdi, [rcx+8]
0x18007f566  mov     esi, edx
0x18007f568  mov     rbx, rcx
0x18007f56b  xor     r15d, r15d
0x18007f56e  mov     rcx, rdi
0x18007f571  mov     [rsp+0A8h+var_34], r15d
0x18007f576  mov     rbp, r8
0x18007f579  lea     rdx, [rdi+68h]
0x18007f57d  call    WapHttp3StreamUpdateTimerOnCompletion
0x18007f582  test    byte ptr cs:xmmword_1800AD720+3, 4
0x18007f589  lea     r14, [rdi+18h]
0x18007f58d  jz      short loc_18007F5A5
0x18007f58f  mov     r9, [r14]
0x18007f592  mov     edx, 0E3h
0x18007f597  mov     ecx, 41Ah
0x18007f59c  mov     dword ptr [rsp+0A8h+var_88], esi
0x18007f5a0  call    WPP_SF_iD
0x18007f5a5  mov     al, byte ptr cs:Microsoft_Windows_WebIOEnableBits+1
0x18007f5ab  test    al, 20h
0x18007f5ad  jz      short loc_18007F609
0x18007f5af  mov     rax, [rbx+90h]
0x18007f5b6  lea     rcx, [rbx+18h]
0x18007f5ba  mov     r8, [rdi+8]
0x18007f5be  lea     rdx, NetSocketRecvEntityComplete
0x18007f5c5  mov     [rsp+0A8h+var_48], r15d
0x18007f5ca  xor     r9d, r9d
0x18007f5cd  mov     [rsp+0A8h+var_50], r15d
0x18007f5d2  mov     [rsp+0A8h+var_58], rax
0x18007f5d7  mov     rax, [r14]
0x18007f5da  mov     [rsp+0A8h+var_60], rax
0x18007f5df  mov     rax, [rbx+88h]
0x18007f5e6  mov     [rsp+0A8h+var_68], rbp
0x18007f5eb  mov     [rsp+0A8h+var_70], esi
0x18007f5ef  mov     [rsp+0A8h+var_78], rcx
0x18007f5f4  mov     [rsp+0A8h+var_80], rax
0x18007f5f9  mov     [rsp+0A8h+var_88], r15
0x18007f5fe  call    McTemplateU0ppxppqxxxtt_EventWriteTransfer
0x18007f603  mov     al, byte ptr cs:Microsoft_Windows_WebIOEnableBits+1
0x18007f609  cmp     esi, 0EAh
0x18007f60f  jnz     loc_18007F760
0x18007f615  cmp     [rbx+84h], r15b
0x18007f61c  jz      short loc_18007F628
0x18007f61e  mov     esi, 54Fh
0x18007f623  jmp     loc_18007F76C
0x18007f628  test    al, 20h
0x18007f62a  jz      short loc_18007F681
0x18007f62c  mov     rax, [rbx+90h]
0x18007f633  lea     rcx, [rbx+18h]
0x18007f637  mov     r8, [rdi+8]
0x18007f63b  lea     rdx, NetSocketRecvEntity
0x18007f642  mov     [rsp+0A8h+var_48], r15d
0x18007f647  xor     r9d, r9d
0x18007f64a  mov     [rsp+0A8h+var_50], r15d
0x18007f64f  mov     [rsp+0A8h+var_58], rax
0x18007f654  mov     rax, [r14]
0x18007f657  mov     [rsp+0A8h+var_60], rax
0x18007f65c  mov     rax, [rbx+88h]
0x18007f663  mov     [rsp+0A8h+var_68], r15
0x18007f668  mov     [rsp+0A8h+var_70], r15d
0x18007f66d  mov     [rsp+0A8h+var_78], rcx
0x18007f672  mov     [rsp+0A8h+var_80], rax
0x18007f677  mov     [rsp+0A8h+var_88], r15
0x18007f67c  call    McTemplateU0ppxppqxxxtt_EventWriteTransfer
0x18007f681  mov     rcx, [rdi+28h]
0x18007f685  mov     rcx, [rcx+8]; pio
0x18007f689  call    cs:__imp_StartThreadpoolIo
0x18007f690  nop     dword ptr [rax+rax+00h]
0x18007f695  mov     rcx, [rdi+28h]
0x18007f699  lea     rax, [rsp+0A8h+var_34]
0x18007f69e  mov     r9, [rbx+88h]
0x18007f6a5  mov     r8d, 1
0x18007f6ab  mov     rdx, [rdi+18h]
0x18007f6af  mov     [rsp+0A8h+var_78], rax
0x18007f6b4  mov     eax, [rbx+90h]
0x18007f6ba  mov     rcx, [rcx]
0x18007f6bd  mov     [rsp+0A8h+var_80], r15
0x18007f6c2  mov     dword ptr [rsp+0A8h+var_88], eax
0x18007f6c6  call    WaHttpApiStreamReceiveEntityBody
0x18007f6cb  mov     rcx, [rdi+28h]
0x18007f6cf  mov     esi, eax
0x18007f6d1  mov     rcx, [rcx+8]; pio
0x18007f6d5  call    cs:__imp_CancelThreadpoolIo
0x18007f6dc  nop     dword ptr [rax+rax+00h]
0x18007f6e1  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+1, 20h
0x18007f6e8  jz      short loc_18007F744
0x18007f6ea  mov     rcx, [rbx+90h]
0x18007f6f1  lea     r9, [rbx+18h]
0x18007f6f5  mov     r8d, [rsp+0A8h+var_34]
0x18007f6fa  lea     rdx, NetSocketRecvEntityComplete
0x18007f701  mov     rax, [rbx+88h]
0x18007f708  mov     [rsp+0A8h+var_48], r15d
0x18007f70d  mov     [rsp+0A8h+var_50], r15d
0x18007f712  mov     [rsp+0A8h+var_58], rcx
0x18007f717  mov     rcx, [rdi+18h]
0x18007f71b  mov     [rsp+0A8h+var_60], rcx
0x18007f720  mov     [rsp+0A8h+var_68], r8
0x18007f725  mov     r8, [rdi+8]
0x18007f729  mov     [rsp+0A8h+var_70], esi
0x18007f72d  mov     [rsp+0A8h+var_78], r9
0x18007f732  xor     r9d, r9d
0x18007f735  mov     [rsp+0A8h+var_80], rax
0x18007f73a  mov     [rsp+0A8h+var_88], r15
0x18007f73f  call    McTemplateU0ppxppqxxxtt_EventWriteTransfer
0x18007f744  cmp     esi, 0EAh
0x18007f74a  jz      loc_18007F835
0x18007f750  cmp     esi, 3E5h
0x18007f756  jz      loc_18007F835
0x18007f75c  mov     ebp, [rsp+0A8h+var_34]
0x18007f760  mov     rdx, rdi
0x18007f763  mov     ecx, esi
0x18007f765  call    WapHttp3StreamGetError
0x18007f76a  mov     esi, eax
0x18007f76c  lea     rcx, [rdi+30h]; lpCriticalSection
0x18007f770  call    cs:__imp_EnterCriticalSection
0x18007f777  nop     dword ptr [rax+rax+00h]
0x18007f77c  mov     edx, esi
0x18007f77e  mov     [rdi+130h], r15
0x18007f785  mov     rcx, rdi
0x18007f788  call    WapHttp3StreamCheckForGoawayResend
0x18007f78d  mov     edx, esi
0x18007f78f  mov     rcx, rdi
0x18007f792  call    WapHttp3StreamCheckForDowngrade
0x18007f797  mov     r8d, esi
0x18007f79a  mov     rdx, rbp
0x18007f79d  mov     rcx, rdi
0x18007f7a0  call    WapHttp3StreamCheckForTrailers
0x18007f7a5  mov     edx, esi
0x18007f7a7  mov     rcx, rdi
0x18007f7aa  call    WapHttp3StreamCheckForReset
0x18007f7af  test    esi, esi
0x18007f7b1  jnz     short loc_18007F7C2
0x18007f7b3  test    rbp, rbp
0x18007f7b6  jnz     short loc_18007F7C2
0x18007f7b8  mov     dword ptr [rdi+128h], 3
0x18007f7c2  lea     rcx, [rdi+30h]; lpCriticalSection
0x18007f7c6  call    cs:__imp_LeaveCriticalSection
0x18007f7cd  nop     dword ptr [rax+rax+00h]
0x18007f7d2  mov     [rbx+70h], esi
0x18007f7d5  mov     [rbx+78h], rbp
0x18007f7d9  cmp     [rbx+84h], r15b
0x18007f7e0  jnz     short loc_18007F7FB
0x18007f7e2  mov     rcx, [rbx+68h]
0x18007f7e6  mov     r8, rbp
0x18007f7e9  mov     rax, [rbx+60h]
0x18007f7ed  mov     edx, esi
0x18007f7ef  mov     byte ptr [rbx+84h], 1
0x18007f7f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f7fb  or      eax, 0FFFFFFFFh
0x18007f7fe  lock xadd [rbx+4], eax
0x18007f803  cmp     eax, 1
0x18007f806  jnz     short loc_18007F810
0x18007f808  mov     rcx, rbx
0x18007f80b  call    WapHttpApiFreeIoContext
0x18007f810  mov     rcx, [rsp+0A8h+var_30]
0x18007f815  xor     rcx, rsp; StackCookie
0x18007f818  call    __security_check_cookie
0x18007f81d  mov     rbx, [rsp+0A8h+arg_10]
0x18007f825  add     rsp, 80h
0x18007f82c  pop     r15
0x18007f82e  pop     r14
0x18007f830  pop     rdi
0x18007f831  pop     rsi
0x18007f832  pop     rbp
0x18007f833  retn
0x18007f835  test    byte ptr cs:xmmword_1800AD710+3, 4
0x18007f83c  jz      loc_18007F61E
0x18007f842  mov     edx, 0E4h
0x18007f847  lea     r8, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x18007f84e  mov     ecx, 21Ah
0x18007f853  mov     r9d, esi
0x18007f856  call    WPP_SF_d
0x18007f85b  jmp     loc_18007F61E
```
