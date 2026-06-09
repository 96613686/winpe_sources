# LegacyTransaction::OnINetCallback(int)

- ea: `0x180053590`
- end: `0x180053946`
- name: `?OnINetCallback@LegacyTransaction@@UEAAJH@Z`
- size: `950`
- prototype: `__int64 __fastcall(LegacyTransaction *__hidden this, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180053590`
- `0x180053950`
- `0x1800547c4`
- `0x18005486c`
- `0x1800e9320`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053630`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053638`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053690`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800536bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053755`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053779`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800537cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053630`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053638`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053690`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800536bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053755`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053779`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800537cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800535ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005361e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005366e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180053769`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800537bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800535ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005361e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005366e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180053769`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800537bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800535bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800535f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800535bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800535f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800537f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053800`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800537f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053800`

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
                  McGenEventWrite_EventWriteTransfer(v17, URLMON_CTRANSACTION_GET_NEXT_CTRANSPACKET, v9, 3, v21);
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
                   *((unsigned int *)this + 95),
                   *(unsigned int *)(v10 + 24),
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
          McTemplateU0qz_EventWriteTransfer(v8, URLMON_CTRANSACTION_GET_NEXT_CTRANSPACKET, 0, *((_QWORD *)this + 32));
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
0x180053590  push    rbp
0x180053592  push    rdi
0x180053593  push    r13
0x180053595  sub     rsp, 90h
0x18005359c  mov     rax, cs:__security_cookie
0x1800535a3  xor     rax, rsp
0x1800535a6  mov     [rsp+0A8h+var_30], rax
0x1800535ab  xor     r13d, r13d
0x1800535ae  mov     rdi, rcx
0x1800535b1  mov     ebp, r13d
0x1800535b4  test    edx, edx
0x1800535b6  jnz     loc_1800536F5
0x1800535bc  call    cs:__imp_GetCurrentThreadId
0x1800535c2  cmp     [rdi+178h], eax
0x1800535c8  jnz     loc_1800536DA
0x1800535ce  mov     [rsp+0A8h+arg_8], rbx
0x1800535d6  lea     rcx, [rdi+298h]; lpCriticalSection
0x1800535dd  mov     [rsp+0A8h+arg_10], rsi
0x1800535e5  mov     [rsp+0A8h+arg_18], r12
0x1800535ed  call    cs:__imp_EnterCriticalSection
0x1800535f3  mov     esi, [rdi+178h]
0x1800535f9  call    cs:__imp_GetCurrentThreadId
0x1800535ff  cmp     esi, eax
0x180053601  jnz     loc_1800536B5
0x180053607  test    byte ptr [rdi+1B8h], 4
0x18005360e  jnz     loc_1800536B5
0x180053614  lea     rsi, [rdi+220h]
0x18005361b  mov     rcx, rsi; lpCriticalSection
0x18005361e  call    cs:__imp_EnterCriticalSection
0x180053624  mov     rcx, rsi; lpCriticalSection
0x180053627  cmp     [rdi+180h], rbp
0x18005362e  jnz     short loc_180053638
0x180053630  call    cs:__imp_LeaveCriticalSection
0x180053636  jmp     short loc_1800536B5
0x180053638  call    cs:__imp_LeaveCriticalSection
0x18005363e  or      byte ptr [rdi+1B8h], 4
0x180053645  mov     r12d, [rdi+1B0h]
0x18005364c  test    r12d, 0FFFFFFFDh
0x180053653  jnz     short loc_1800536AE
0x180053655  mov     [rsp+0A8h+var_20], r14
0x18005365d  mov     [rsp+0A8h+var_28], r15
0x180053665  mov     r15d, 1
0x18005366b  mov     rcx, rsi; lpCriticalSection
0x18005366e  call    cs:__imp_EnterCriticalSection
0x180053674  mov     r14, [rdi+180h]
0x18005367b  test    r14, r14
0x18005367e  jnz     loc_180053838
0x180053684  test    byte ptr cs:Microsoft_Windows_URLMonEnableBits, 1
0x18005368b  jnz     short loc_180053701
0x18005368d  mov     rcx, rsi; lpCriticalSection
0x180053690  call    cs:__imp_LeaveCriticalSection
0x180053696  mov     r15, [rsp+0A8h+var_28]
0x18005369e  mov     r14, [rsp+0A8h+var_20]
0x1800536a6  cmp     ebp, 800C0018h
0x1800536ac  jz      short loc_18005371C
0x1800536ae  and     byte ptr [rdi+1B8h], 0FBh
0x1800536b5  lea     rcx, [rdi+298h]; lpCriticalSection
0x1800536bc  call    cs:__imp_LeaveCriticalSection
0x1800536c2  mov     r12, [rsp+0A8h+arg_18]
0x1800536ca  mov     rsi, [rsp+0A8h+arg_10]
0x1800536d2  mov     rbx, [rsp+0A8h+arg_8]
0x1800536da  mov     eax, ebp
0x1800536dc  mov     rcx, [rsp+0A8h+var_30]
0x1800536e1  xor     rcx, rsp; StackCookie
0x1800536e4  call    __security_check_cookie
0x1800536e9  add     rsp, 90h
0x1800536f0  pop     r13
0x1800536f2  pop     rdi
0x1800536f3  pop     rbp
0x1800536f4  retn
0x1800536f5  lock dec dword ptr [rcx+1ACh]
0x1800536fc  jmp     loc_1800535BC
0x180053701  mov     r9, [rdi+100h]
0x180053708  lea     rdx, URLMON_CTRANSACTION_GET_NEXT_CTRANSPACKET
0x18005370f  xor     r8d, r8d
0x180053712  call    McTemplateU0qz_EventWriteTransfer
0x180053717  jmp     loc_18005368D
0x18005371c  mov     ebp, r13d
0x18005371f  jmp     short loc_1800536B5
0x180053721  lea     eax, ds:2[rax*2]
0x180053728  mov     [rsp+0A8h+var_38], eax
0x18005372c  lea     rdx, URLMON_CTRANSACTION_GET_NEXT_CTRANSPACKET
0x180053733  lea     rax, [rsp+0A8h+var_60]
0x180053738  mov     [rsp+0A8h+var_40], rcx
0x18005373d  mov     r9d, 3
0x180053743  mov     qword ptr [rsp+0A8h+var_88], rax
0x180053748  mov     [rsp+0A8h+var_34], r13d
0x18005374d  call    McGenEventWrite_EventWriteTransfer
0x180053752  mov     rcx, rsi; jumptable 00000001800538F8 cases 1,2,11,33-46
0x180053755  call    cs:__imp_LeaveCriticalSection
0x18005375b  cmp     dword ptr [r14+34h], 3Bh ; ';'
0x180053760  jz      loc_180053814
0x180053766  mov     rcx, rsi; lpCriticalSection
0x180053769  call    cs:__imp_EnterCriticalSection
0x18005376f  mov     rcx, rsi; lpCriticalSection
0x180053772  mov     [rdi+190h], r14
0x180053779  call    cs:__imp_LeaveCriticalSection
0x18005377f  mov     eax, [r14+30h]
0x180053783  mov     rcx, rdi; this
0x180053786  mov     r9d, [r14+18h]; unsigned int
0x18005378a  mov     r8d, [rdi+17Ch]; unsigned int
0x180053791  mov     edx, [r14+34h]; enum tagBINDSTATUS
0x180053795  mov     [rsp+0A8h+var_70], eax; int
0x180053799  mov     eax, [r14+20h]
0x18005379d  mov     [rsp+0A8h+var_78], eax; unsigned int
0x1800537a1  mov     rax, [r14+28h]
0x1800537a5  mov     [rsp+0A8h+var_80], rax; unsigned __int16 *
0x1800537aa  mov     eax, [r14+1Ch]
0x1800537ae  mov     [rsp+0A8h+var_88], eax; unsigned int
0x1800537b2  call    ?DispatchReport@CTransaction@@QEAAJW4tagBINDSTATUS@@KKKPEBGKJ@Z; CTransaction::DispatchReport(tagBINDSTATUS,ulong,ulong,ulong,ushort const *,ulong,long)
0x1800537b7  mov     rcx, rsi; lpCriticalSection
0x1800537ba  mov     ebp, eax
0x1800537bc  call    cs:__imp_EnterCriticalSection
0x1800537c2  mov     rcx, rsi; lpCriticalSection
0x1800537c5  mov     [rdi+190h], r13
0x1800537cc  call    cs:__imp_LeaveCriticalSection
0x1800537d2  test    r12d, r12d
0x1800537d5  jnz     short loc_1800537E2
0x1800537d7  cmp     dword ptr [rdi+1B0h], 1
0x1800537de  cmovz   r15d, r13d
0x1800537e2  cmp     ebp, 800C0018h
0x1800537e8  jz      loc_1800538FA
0x1800537ee  mov     rcx, [r14+28h]; pv
0x1800537f2  test    rcx, rcx
0x1800537f5  jz      short loc_1800537FD
0x1800537f7  call    cs:__imp_CoTaskMemFree
0x1800537fd  mov     rcx, r14; pv
0x180053800  call    cs:__imp_CoTaskMemFree
0x180053806  test    r15d, r15d
0x180053809  jnz     loc_18005366B
0x18005380f  jmp     loc_180053696
0x180053814  lock dec dword ptr [rdi+1ACh]
0x18005381b  mov     rcx, [rdi+138h]
0x180053822  test    rcx, rcx
0x180053825  jz      short loc_1800537D2
0x180053827  mov     rax, [rcx]
0x18005382a  mov     rdx, r14
0x18005382d  mov     rax, [rax+20h]
0x180053831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053836  jmp     short loc_1800537D2
0x180053838  cmp     r14, [rdi+188h]
0x18005383f  jnz     loc_1800538D2
0x180053845  mov     [rdi+188h], r13
0x18005384c  mov     rax, r13
0x18005384f  mov     [rdi+180h], rax
0x180053856  lock dec dword ptr [rdi+1A8h]
0x18005385d  mov     edx, [r14+34h]
0x180053861  cmp     edx, 2Fh ; '/'
0x180053864  jz      loc_180053752; jumptable 00000001800538F8 cases 1,2,11,33-46
0x18005386a  lea     eax, [rdx-1]; switch 46 cases
0x18005386d  cmp     eax, 2Dh
0x180053870  jbe     short loc_1800538DB
0x180053872  test    byte ptr cs:Microsoft_Windows_URLMonEnableBits, 1; jumptable 00000001800538F8 default case, cases 3-10,12-32
0x180053879  jz      loc_180053752; jumptable 00000001800538F8 cases 1,2,11,33-46
0x18005387f  mov     rcx, [rdi+100h]
0x180053886  lea     rax, [rsp+0A8h+var_68]
0x18005388b  mov     [rsp+0A8h+var_68], edx
0x18005388f  mov     [rsp+0A8h+var_50], rax
0x180053894  mov     [rsp+0A8h+var_48], 4
0x18005389d  test    rcx, rcx
0x1800538a0  jz      short loc_1800538C1
0x1800538a2  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800538a9  nop     dword ptr [rax+00000000h]
0x1800538b0  cmp     [rcx+rax*2+2], r13w
0x1800538b6  lea     rax, [rax+1]
0x1800538ba  jnz     short loc_1800538B0
0x1800538bc  jmp     loc_180053721
0x1800538c1  mov     eax, 0Ah
0x1800538c6  lea     rcx, aNull_1; "NULL"
0x1800538cd  jmp     loc_180053728
0x1800538d2  mov     rax, [r14+38h]
0x1800538d6  jmp     loc_18005384F
0x1800538db  lea     r8, __ImageBase
0x1800538e2  cdqe
0x1800538e4  movzx   eax, ds:(byte_180053918 - 180000000h)[r8+rax]
0x1800538ed  mov     ecx, ds:(jpt_1800538F8 - 180000000h)[r8+rax*4]
0x1800538f5  add     rcx, r8
0x1800538f8  jmp     rcx; switch jump
0x1800538fa  mov     rdx, r14; struct CTransPacket *
0x1800538fd  mov     rcx, rdi; this
0x180053900  call    ?SuspendDispatchingPackets@CTransaction@@QEAAXPEAVCTransPacket@@@Z; CTransaction::SuspendDispatchingPackets(CTransPacket *)
0x180053905  mov     r15d, r13d
0x180053908  jmp     loc_1800537EE
```
