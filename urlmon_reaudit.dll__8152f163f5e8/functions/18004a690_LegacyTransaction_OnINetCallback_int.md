# LegacyTransaction::OnINetCallback(int)

- ea: `0x18004a690`
- end: `0x18004aaaa`
- name: `?OnINetCallback@LegacyTransaction@@UEAAJH@Z`
- size: `1050`
- prototype: `__int64 __fastcall(LegacyTransaction *__hidden this, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18004a690`
- `0x18004aab0`
- `0x18004b9b8`
- `0x18004bab4`
- `0x1800f31d0`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a748`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a759`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a7c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a7f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a893`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a8c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a922`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a748`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a759`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a7c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a7f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a893`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a8c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a922`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a6f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a730`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a795`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a8ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a90c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a6f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a730`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a795`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a8ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a90c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004a6bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004a705`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004a6bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004a705`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a953`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a962`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a953`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a962`

## pseudocode

```c
__int64 __fastcall LegacyTransaction::OnINetCallback(LegacyTransaction *this, int a2)
{
  unsigned int v3; // ebp
  int v4; // esi
  struct _RTL_CRITICAL_SECTION *v5; // rcx
  int v6; // r12d
  int v7; // r15d
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r14
  int v12; // eax
  void *v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rax
  int v16; // edx
  const wchar_t *v17; // rcx
  __int64 v18; // rax
  int v20; // [rsp+40h] [rbp-68h] BYREF
  _BYTE v21[16]; // [rsp+48h] [rbp-60h] BYREF
  int *v22; // [rsp+58h] [rbp-50h]
  __int64 v23; // [rsp+60h] [rbp-48h]
  const wchar_t *v24; // [rsp+68h] [rbp-40h]
  int v25; // [rsp+70h] [rbp-38h]
  int v26; // [rsp+74h] [rbp-34h]

  v3 = 0;
  if ( a2 )
    _InterlockedDecrement((volatile signed __int32 *)this + 107);
  if ( *((_DWORD *)this + 94) == GetCurrentThreadId() )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 664));
    v4 = *((_DWORD *)this + 94);
    if ( v4 == GetCurrentThreadId() && (*((_BYTE *)this + 440) & 4) == 0 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 544));
      v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 544);
      if ( *((_QWORD *)this + 48) )
      {
        LeaveCriticalSection(v5);
        *((_BYTE *)this + 440) |= 4u;
        v6 = *((_DWORD *)this + 108);
        if ( (v6 & 0xFFFFFFFD) != 0 )
          goto LABEL_15;
        v7 = 1;
        while ( 1 )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 544));
          v10 = *((_QWORD *)this + 48);
          if ( !v10 )
            break;
          if ( v10 == *((_QWORD *)this + 49) )
          {
            *((_QWORD *)this + 49) = 0;
            v15 = 0;
          }
          else
          {
            v15 = *(_QWORD *)(v10 + 56);
          }
          *((_QWORD *)this + 48) = v15;
          _InterlockedDecrement((volatile signed __int32 *)this + 106);
          v16 = *(_DWORD *)(v10 + 52);
          if ( v16 != 47 )
          {
            switch ( v16 )
            {
              case 1:
              case 2:
              case 11:
              case 33:
              case 34:
              case 35:
              case 36:
              case 37:
              case 38:
              case 39:
              case 40:
              case 41:
              case 42:
              case 43:
              case 44:
              case 45:
              case 46:
                break;
              default:
                if ( (Microsoft_Windows_URLMonEnableBits & 1) != 0 )
                {
                  v17 = (const wchar_t *)*((_QWORD *)this + 32);
                  v20 = *(_DWORD *)(v10 + 52);
                  v22 = &v20;
                  v23 = 4;
                  if ( v17 )
                  {
                    v18 = -1;
                    while ( v17[++v18] != 0 )
                      ;
                    v12 = 2 * v18 + 2;
                  }
                  else
                  {
                    v12 = 10;
                    v17 = L"NULL";
                  }
                  v25 = v12;
                  v24 = v17;
                  v26 = 0;
                  McGenEventWrite_EventWriteTransfer(v17, &URLMON_CTRANSACTION_GET_NEXT_CTRANSPACKET, v9, 3, v21);
                }
                break;
            }
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 544));
          if ( *(_DWORD *)(v10 + 52) == 59 )
          {
            _InterlockedDecrement((volatile signed __int32 *)this + 107);
            v14 = *((_QWORD *)this + 39);
            if ( v14 )
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 32LL))(v14, v10);
          }
          else
          {
            EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 544));
            *((_QWORD *)this + 50) = v10;
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 544));
            v3 = CTransaction::DispatchReport(
                   this,
                   *(_DWORD *)(v10 + 52),
                   *((_DWORD *)this + 95),
                   *(_DWORD *)(v10 + 24),
                   *(_DWORD *)(v10 + 28),
                   *(LPCWSTR *)(v10 + 40),
                   *(_DWORD *)(v10 + 32),
                   *(_DWORD *)(v10 + 48));
            EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 544));
            *((_QWORD *)this + 50) = 0;
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 544));
          }
          if ( !v6 && *((_DWORD *)this + 108) == 1 )
            v7 = 0;
          if ( v3 == -2146697192 )
          {
            CTransaction::SuspendDispatchingPackets(this, (struct CTransPacket *)v10);
            v7 = 0;
          }
          v13 = *(void **)(v10 + 40);
          if ( v13 )
            CoTaskMemFree(v13);
          CoTaskMemFree((LPVOID)v10);
          if ( !v7 )
            goto LABEL_14;
        }
        if ( (Microsoft_Windows_URLMonEnableBits & 1) != 0 )
          McTemplateU0qz_EventWriteTransfer(v8, &URLMON_CTRANSACTION_GET_NEXT_CTRANSPACKET, 0, *((_QWORD *)this + 32));
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 544));
LABEL_14:
        if ( v3 == -2146697192 )
          v3 = 0;
        else
LABEL_15:
          *((_BYTE *)this + 440) &= ~4u;
      }
      else
      {
        LeaveCriticalSection(v5);
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 664));
  }
  return v3;
}

```

## disassembly

```asm
0x18004a690  push    rbp
0x18004a692  push    rdi
0x18004a693  push    r13
0x18004a695  sub     rsp, 90h
0x18004a69c  mov     rax, cs:__security_cookie
0x18004a6a3  xor     rax, rsp
0x18004a6a6  mov     [rsp+0A8h+var_30], rax
0x18004a6ab  xor     r13d, r13d
0x18004a6ae  mov     rdi, rcx
0x18004a6b1  mov     ebp, r13d
0x18004a6b4  test    edx, edx
0x18004a6b6  jnz     loc_18004A833
0x18004a6bc  call    cs:__imp_GetCurrentThreadId
0x18004a6c3  nop     dword ptr [rax+rax+00h]
0x18004a6c8  cmp     [rdi+178h], eax
0x18004a6ce  jnz     loc_18004A817
0x18004a6d4  mov     [rsp+0A8h+arg_8], rbx
0x18004a6dc  lea     rcx, [rdi+298h]; lpCriticalSection
0x18004a6e3  mov     [rsp+0A8h+arg_10], rsi
0x18004a6eb  mov     [rsp+0A8h+arg_18], r12
0x18004a6f3  call    cs:__imp_EnterCriticalSection
0x18004a6fa  nop     dword ptr [rax+rax+00h]
0x18004a6ff  mov     esi, [rdi+178h]
0x18004a705  call    cs:__imp_GetCurrentThreadId
0x18004a70c  nop     dword ptr [rax+rax+00h]
0x18004a711  cmp     esi, eax
0x18004a713  jnz     loc_18004A7EC
0x18004a719  test    byte ptr [rdi+1B8h], 4
0x18004a720  jnz     loc_18004A7EC
0x18004a726  lea     rsi, [rdi+220h]
0x18004a72d  mov     rcx, rsi; lpCriticalSection
0x18004a730  call    cs:__imp_EnterCriticalSection
0x18004a737  nop     dword ptr [rax+rax+00h]
0x18004a73c  mov     rcx, rsi; lpCriticalSection
0x18004a73f  cmp     [rdi+180h], rbp
0x18004a746  jnz     short loc_18004A759
0x18004a748  call    cs:__imp_LeaveCriticalSection
0x18004a74f  nop     dword ptr [rax+rax+00h]
0x18004a754  jmp     loc_18004A7EC
0x18004a759  call    cs:__imp_LeaveCriticalSection
0x18004a760  nop     dword ptr [rax+rax+00h]
0x18004a765  or      byte ptr [rdi+1B8h], 4
0x18004a76c  mov     r12d, [rdi+1B0h]
0x18004a773  test    r12d, 0FFFFFFFDh
0x18004a77a  jnz     short loc_18004A7E5
0x18004a77c  mov     [rsp+0A8h+var_20], r14
0x18004a784  mov     [rsp+0A8h+var_28], r15
0x18004a78c  mov     r15d, 1
0x18004a792  mov     rcx, rsi; lpCriticalSection
0x18004a795  call    cs:__imp_EnterCriticalSection
0x18004a79c  nop     dword ptr [rax+rax+00h]
0x18004a7a1  mov     r14, [rdi+180h]
0x18004a7a8  test    r14, r14
0x18004a7ab  jnz     loc_18004A9A0
0x18004a7b1  test    byte ptr cs:Microsoft_Windows_URLMonEnableBits, 1
0x18004a7b8  jnz     loc_18004A83F
0x18004a7be  mov     rcx, rsi; lpCriticalSection
0x18004a7c1  call    cs:__imp_LeaveCriticalSection
0x18004a7c8  nop     dword ptr [rax+rax+00h]
0x18004a7cd  mov     r15, [rsp+0A8h+var_28]
0x18004a7d5  mov     r14, [rsp+0A8h+var_20]
0x18004a7dd  cmp     ebp, 800C0018h
0x18004a7e3  jz      short loc_18004A85A
0x18004a7e5  and     byte ptr [rdi+1B8h], 0FBh
0x18004a7ec  lea     rcx, [rdi+298h]; lpCriticalSection
0x18004a7f3  call    cs:__imp_LeaveCriticalSection
0x18004a7fa  nop     dword ptr [rax+rax+00h]
0x18004a7ff  mov     r12, [rsp+0A8h+arg_18]
0x18004a807  mov     rsi, [rsp+0A8h+arg_10]
0x18004a80f  mov     rbx, [rsp+0A8h+arg_8]
0x18004a817  mov     eax, ebp
0x18004a819  mov     rcx, [rsp+0A8h+var_30]
0x18004a81e  xor     rcx, rsp; StackCookie
0x18004a821  call    __security_check_cookie
0x18004a826  add     rsp, 90h
0x18004a82d  pop     r13
0x18004a82f  pop     rdi
0x18004a830  pop     rbp
0x18004a831  retn
0x18004a833  lock dec dword ptr [rcx+1ACh]
0x18004a83a  jmp     loc_18004A6BC
0x18004a83f  mov     r9, [rdi+100h]
0x18004a846  lea     rdx, URLMON_CTRANSACTION_GET_NEXT_CTRANSPACKET
0x18004a84d  xor     r8d, r8d
0x18004a850  call    McTemplateU0qz_EventWriteTransfer
0x18004a855  jmp     loc_18004A7BE
0x18004a85a  mov     ebp, r13d
0x18004a85d  jmp     short loc_18004A7EC
0x18004a85f  lea     eax, ds:2[rax*2]
0x18004a866  mov     [rsp+0A8h+var_38], eax
0x18004a86a  lea     rdx, URLMON_CTRANSACTION_GET_NEXT_CTRANSPACKET
0x18004a871  lea     rax, [rsp+0A8h+var_60]
0x18004a876  mov     [rsp+0A8h+var_40], rcx
0x18004a87b  mov     r9d, 3
0x18004a881  mov     qword ptr [rsp+0A8h+var_88], rax
0x18004a886  mov     [rsp+0A8h+var_34], r13d
0x18004a88b  call    McGenEventWrite_EventWriteTransfer
0x18004a890  mov     rcx, rsi; jumptable 000000018004AA59 cases 1,2,11,33-46
0x18004a893  call    cs:__imp_LeaveCriticalSection
0x18004a89a  nop     dword ptr [rax+rax+00h]
0x18004a89f  cmp     dword ptr [r14+34h], 3Bh ; ';'
0x18004a8a4  jz      loc_18004A97C
0x18004a8aa  mov     rcx, rsi; lpCriticalSection
0x18004a8ad  call    cs:__imp_EnterCriticalSection
0x18004a8b4  nop     dword ptr [rax+rax+00h]
0x18004a8b9  mov     rcx, rsi; lpCriticalSection
0x18004a8bc  mov     [rdi+190h], r14
0x18004a8c3  call    cs:__imp_LeaveCriticalSection
0x18004a8ca  nop     dword ptr [rax+rax+00h]
0x18004a8cf  mov     eax, [r14+30h]
0x18004a8d3  mov     rcx, rdi; this
0x18004a8d6  mov     r9d, [r14+18h]; unsigned int
0x18004a8da  mov     r8d, [rdi+17Ch]; unsigned int
0x18004a8e1  mov     edx, [r14+34h]; enum tagBINDSTATUS
0x18004a8e5  mov     [rsp+0A8h+var_70], eax; int
0x18004a8e9  mov     eax, [r14+20h]
0x18004a8ed  mov     [rsp+0A8h+var_78], eax; unsigned int
0x18004a8f1  mov     rax, [r14+28h]
0x18004a8f5  mov     [rsp+0A8h+var_80], rax; unsigned __int16 *
0x18004a8fa  mov     eax, [r14+1Ch]
0x18004a8fe  mov     [rsp+0A8h+var_88], eax; unsigned int
0x18004a902  call    ?DispatchReport@CTransaction@@QEAAJW4tagBINDSTATUS@@KKKPEBGKJ@Z; CTransaction::DispatchReport(tagBINDSTATUS,ulong,ulong,ulong,ushort const *,ulong,long)
0x18004a907  mov     rcx, rsi; lpCriticalSection
0x18004a90a  mov     ebp, eax
0x18004a90c  call    cs:__imp_EnterCriticalSection
0x18004a913  nop     dword ptr [rax+rax+00h]
0x18004a918  mov     rcx, rsi; lpCriticalSection
0x18004a91b  mov     [rdi+190h], r13
0x18004a922  call    cs:__imp_LeaveCriticalSection
0x18004a929  nop     dword ptr [rax+rax+00h]
0x18004a92e  test    r12d, r12d
0x18004a931  jnz     short loc_18004A93E
0x18004a933  cmp     dword ptr [rdi+1B0h], 1
0x18004a93a  cmovz   r15d, r13d
0x18004a93e  cmp     ebp, 800C0018h
0x18004a944  jz      loc_18004AA5F
0x18004a94a  mov     rcx, [r14+28h]; pv
0x18004a94e  test    rcx, rcx
0x18004a951  jz      short loc_18004A95F
0x18004a953  call    cs:__imp_CoTaskMemFree
0x18004a95a  nop     dword ptr [rax+rax+00h]
0x18004a95f  mov     rcx, r14; pv
0x18004a962  call    cs:__imp_CoTaskMemFree
0x18004a969  nop     dword ptr [rax+rax+00h]
0x18004a96e  test    r15d, r15d
0x18004a971  jnz     loc_18004A792
0x18004a977  jmp     loc_18004A7CD
0x18004a97c  lock dec dword ptr [rdi+1ACh]
0x18004a983  mov     rcx, [rdi+138h]
0x18004a98a  test    rcx, rcx
0x18004a98d  jz      short loc_18004A92E
0x18004a98f  mov     rax, [rcx]
0x18004a992  mov     rdx, r14
0x18004a995  mov     rax, [rax+20h]
0x18004a999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a99e  jmp     short loc_18004A92E
0x18004a9a0  cmp     r14, [rdi+188h]
0x18004a9a7  jnz     loc_18004AA33
0x18004a9ad  mov     [rdi+188h], r13
0x18004a9b4  mov     rax, r13
0x18004a9b7  mov     [rdi+180h], rax
0x18004a9be  lock dec dword ptr [rdi+1A8h]
0x18004a9c5  mov     edx, [r14+34h]
0x18004a9c9  cmp     edx, 2Fh ; '/'
0x18004a9cc  jz      loc_18004A890; jumptable 000000018004AA59 cases 1,2,11,33-46
0x18004a9d2  lea     eax, [rdx-1]; switch 46 cases
0x18004a9d5  cmp     eax, 2Dh
0x18004a9d8  jbe     short loc_18004AA3C
0x18004a9da  test    byte ptr cs:Microsoft_Windows_URLMonEnableBits, 1; jumptable 000000018004AA59 default case, cases 3-10,12-32
0x18004a9e1  jz      loc_18004A890; jumptable 000000018004AA59 cases 1,2,11,33-46
0x18004a9e7  mov     rcx, [rdi+100h]
0x18004a9ee  lea     rax, [rsp+0A8h+var_68]
0x18004a9f3  mov     [rsp+0A8h+var_68], edx
0x18004a9f7  mov     [rsp+0A8h+var_50], rax
0x18004a9fc  mov     [rsp+0A8h+var_48], 4
0x18004aa05  test    rcx, rcx
0x18004aa08  jz      short loc_18004AA22
0x18004aa0a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18004aa11  cmp     [rcx+rax*2+2], r13w
0x18004aa17  lea     rax, [rax+1]
0x18004aa1b  jnz     short loc_18004AA11
0x18004aa1d  jmp     loc_18004A85F
0x18004aa22  mov     eax, 0Ah
0x18004aa27  lea     rcx, aNull_1; "NULL"
0x18004aa2e  jmp     loc_18004A866
0x18004aa33  mov     rax, [r14+38h]
0x18004aa37  jmp     loc_18004A9B7
0x18004aa3c  lea     r8, __ImageBase
0x18004aa43  cdqe
0x18004aa45  movzx   eax, ds:(byte_18004AA7C - 180000000h)[r8+rax]
0x18004aa4e  mov     ecx, ds:(jpt_18004AA59 - 180000000h)[r8+rax*4]
0x18004aa56  add     rcx, r8
0x18004aa59  jmp     rcx; switch jump
0x18004aa5f  mov     rdx, r14; struct CTransPacket *
0x18004aa62  mov     rcx, rdi; this
0x18004aa65  call    ?SuspendDispatchingPackets@CTransaction@@QEAAXPEAVCTransPacket@@@Z; CTransaction::SuspendDispatchingPackets(CTransPacket *)
0x18004aa6a  mov     r15d, r13d
0x18004aa6d  jmp     loc_18004A94A
```
