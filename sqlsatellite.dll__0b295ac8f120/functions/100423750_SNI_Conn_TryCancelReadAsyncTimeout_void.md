# SNI_Conn::TryCancelReadAsyncTimeout(void)

- ea: `0x100423750`
- end: `0x100423a51`
- name: `?TryCancelReadAsyncTimeout@SNI_Conn@@QEAAXXZ`
- size: `769`
- prototype: `void __fastcall(SNI_Conn *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x100426110`
- `0x100426350`
- `0x100447930`

## callees

- `0x100423750`
- `0x100429580`
- `0x100429680`
- `0x1004298a0`
- `0x10042c270`
- `0x10042c430`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10042385f`
- `KERNEL32!QueryPerformanceCounter` at `0x1004238b8`
- `KERNEL32!QueryPerformanceCounter` at `0x100423915`
- `KERNEL32!QueryPerformanceCounter` at `0x10042385f`
- `KERNEL32!QueryPerformanceCounter` at `0x1004238b8`
- `KERNEL32!QueryPerformanceCounter` at `0x100423915`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100423979`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10042384c`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1004238a4`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100423901`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100423877`
- `sqldk!SystemThread_TlsIndex` at `0x10042381e`
- `sqldk!SystemThread_TlsOffset` at `0x100423827`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1004237fe`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100423985`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100423985`

## string_xrefs

- `0x10042376b`: `sql\common\dk\sni\src\sni.cpp`
- `0x100423777`: `SNI_Conn::TryCancelReadAsyncTimeout`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall SNI_Conn::TryCancelReadAsyncTimeout(SNI_Conn *this, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned __int64 v5; // rdi
  LARGE_INTEGER v6; // rbx
  signed __int64 UniqueThread_low; // r15
  __int64 v8; // rbp
  __int64 v9; // r8
  unsigned __int64 v10; // rcx
  LARGE_INTEGER v11; // rcx
  LONGLONG v12; // rax
  LARGE_INTEGER v13; // rax
  LONGLONG v14; // rcx
  int v15; // eax
  struct SNI_ReadTimeoutListBlock *v16; // r8
  LARGE_INTEGER PerformanceCount; // [rsp+98h] [rbp+10h] BYREF
  LARGE_INTEGER v18; // [rsp+A0h] [rbp+18h] BYREF
  LARGE_INTEGER v19; // [rsp+A8h] [rbp+20h] BYREF

  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\sni.cpp",
      "SNI_Conn::TryCancelReadAsyncTimeout",
      1452,
      L"API|SNI",
      -2);
  if ( *((_BYTE *)this + 12568) )
  {
    v5 = *((_QWORD *)this + 1570);
    if ( v5 )
    {
      v6.QuadPart = 0;
      UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      if ( *(_DWORD *)(v5 + 16)
        || _InterlockedCompareExchange64((volatile signed __int64 *)(v5 + 16), UniqueThread_low, 0) )
      {
        v8 = 0;
        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
        {
          v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          if ( v9 && *(_QWORD *)(v9 + 272) == v9 )
            v8 = *(_QWORD *)(v9 + 256);
          if ( v8 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&PerformanceCount);
              v6 = PerformanceCount;
            }
            else
            {
              v6.QuadPart = MEMORY[0x7FFE0008];
            }
          }
        }
        v10 = v5 + 16;
        if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
          Spinlock<250,3,258>::SpinToAcquireWithExponentialBackoff(v10, UniqueThread_low);
        else
          Spinlock<250,3,258>::SpinToAcquireOptimistic(v10, v8, UniqueThread_low);
        if ( v8 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v18);
            v11 = v18;
          }
          else
          {
            v11.QuadPart = MEMORY[0x7FFE0008];
          }
          v12 = 0;
          if ( v11.QuadPart >= (unsigned __int64)v6.QuadPart )
            v12 = v11.QuadPart - v6.QuadPart;
          *(_QWORD *)(v8 + 3192) += v12;
        }
      }
      if ( !*((_BYTE *)this + 12584) )
      {
        *((_QWORD *)this + 1570) = 0;
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v19);
          v13 = v19;
        }
        else
        {
          v13.QuadPart = MEMORY[0x7FFE0008];
        }
        if ( *(_QWORD *)(v5 + 8) - v13.QuadPart < 0 )
        {
          *((_BYTE *)this + 12584) = 1;
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1577) + 88LL))(*((_QWORD *)this + 1577));
          v14 = 0;
        }
        else
        {
          v14 = 0;
          if ( *(_QWORD *)(v5 + 8) >= v13.QuadPart )
            v14 = *(_QWORD *)(v5 + 8) - v13.QuadPart;
        }
        *((_QWORD *)this + 1572) = v14;
        _InterlockedDecrement16((volatile signed __int16 *)(v5 + 24));
      }
      if ( v5 != -16 )
      {
        if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v15 = rand();
          if ( v15 == 5 * (v15 / 5) )
            Spinlock<250,3,258>::UpdateStatSnapshot();
        }
        *(_QWORD *)(v5 + 16) = 0;
      }
      if ( _InterlockedExchangeAdd16((volatile signed __int16 *)(v5 + 24), 0xFFFFu) == 1 )
      {
        *((_QWORD *)this + 1570) = 0;
        *(_QWORD *)v5 = 0;
        v16 = g_pReadTimeoutBlockHead;
        a4 = 0x6666666666666667LL;
        while ( v5 < (unsigned __int64)v16 + 16 || (unsigned __int64)((__int64)(v5 - (_QWORD)v16 - 16) / 40) >= 0x1FE0 )
        {
          v16 = *(struct SNI_ReadTimeoutListBlock **)v16;
          if ( !v16 )
            goto LABEL_47;
        }
        _InterlockedDecrement16((volatile signed __int16 *)v16 + 4);
      }
    }
  }
LABEL_47:
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON(
      "sql\\common\\dk\\sni\\src\\sni.cpp",
      "SNI_Conn::TryCancelReadAsyncTimeout",
      1452,
      (const wchar_t *)a4);
}

```

## disassembly

```asm
0x100423750  push    rbx
0x100423752  push    rbp
0x100423753  push    rsi
0x100423754  push    rdi
0x100423755  push    r12
0x100423757  push    r14
0x100423759  push    r15
0x10042375b  sub     rsp, 50h
0x10042375f  mov     [rsp+88h+var_68], 0FFFFFFFFFFFFFFFEh
0x100423768  mov     rsi, rcx
0x10042376b  lea     rcx, aSqlCommonDkSni_13; "sql\\common\\dk\\sni\\src\\sni.cpp"
0x100423772  mov     [rsp+88h+var_50], rcx
0x100423777  lea     rdx, aSniConnTrycanc; "SNI_Conn::TryCancelReadAsyncTimeout"
0x10042377e  mov     [rsp+88h+var_48], rdx
0x100423783  mov     [rsp+88h+var_40], 5ACh
0x10042378b  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100423792  jz      short loc_1004237A6
0x100423794  lea     r9, aApiSni; "API|SNI"
0x10042379b  mov     r8d, 5ACh; int
0x1004237a1  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x1004237a6  cmp     byte ptr [rsi+3118h], 0
0x1004237ad  jz      loc_100423A25
0x1004237b3  mov     rdi, [rsi+3110h]
0x1004237ba  test    rdi, rdi
0x1004237bd  jz      loc_100423A25
0x1004237c3  lea     r14, [rdi+10h]
0x1004237c7  mov     [rsp+88h+var_60], r14
0x1004237cc  xor     r12d, r12d
0x1004237cf  mov     [rsp+88h+var_58], r12d
0x1004237d4  mov     ebx, r12d
0x1004237d7  mov     eax, gs:48h
0x1004237df  mov     r15d, eax
0x1004237e2  mov     eax, [r14]
0x1004237e5  test    eax, eax
0x1004237e7  jnz     short loc_1004237FE
0x1004237e9  xor     eax, eax
0x1004237eb  lock cmpxchg [r14], r15
0x1004237f0  mov     eax, r12d
0x1004237f3  setz    al
0x1004237f6  test    eax, eax
0x1004237f8  jnz     loc_1004238E7
0x1004237fe  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100423805  mov     ecx, [rax]
0x100423807  and     ecx, 84h
0x10042380d  mov     rbp, r12
0x100423810  cmp     cl, 84h
0x100423813  jnz     short loc_100423877
0x100423815  mov     rdx, gs:58h
0x10042381e  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100423825  mov     ecx, [rax]
0x100423827  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10042382e  mov     r8d, [rax]
0x100423831  add     r8, [rdx+rcx*8]
0x100423835  jz      short loc_100423847
0x100423837  cmp     [r8+110h], r8
0x10042383e  jnz     short loc_100423847
0x100423840  mov     rbp, [r8+100h]
0x100423847  test    rbp, rbp
0x10042384a  jz      short loc_100423877
0x10042384c  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100423853  cmp     [rax], ebx
0x100423855  jz      short loc_10042386F
0x100423857  lea     rcx, [rsp+88h+PerformanceCount]; lpPerformanceCount
0x10042385f  call    cs:__imp_QueryPerformanceCounter
0x100423865  mov     rbx, qword ptr [rsp+88h+PerformanceCount]
0x10042386d  jmp     short loc_100423877
0x10042386f  mov     rbx, ds:7FFE0008h
0x100423877  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x10042387e  mov     rcx, r14
0x100423881  cmp     byte ptr [rax+0C7h], 0
0x100423888  jge     short loc_100423897
0x10042388a  mov     r8, r15
0x10042388d  mov     rdx, rbp
0x100423890  call    ?SpinToAcquireOptimistic@?$Spinlock@$0PK@$02$0BAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<250,3,258>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x100423895  jmp     short loc_10042389F
0x100423897  mov     rdx, r15
0x10042389a  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0PK@$02$0BAC@@@AEAAX_K@Z; Spinlock<250,3,258>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10042389f  test    rbp, rbp
0x1004238a2  jz      short loc_1004238E7
0x1004238a4  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004238ab  cmp     dword ptr [rax], 0
0x1004238ae  jz      short loc_1004238C8
0x1004238b0  lea     rcx, [rsp+88h+arg_10]; lpPerformanceCount
0x1004238b8  call    cs:__imp_QueryPerformanceCounter
0x1004238be  mov     rcx, qword ptr [rsp+88h+arg_10]
0x1004238c6  jmp     short loc_1004238D0
0x1004238c8  mov     rcx, ds:7FFE0008h
0x1004238d0  mov     rdx, rcx
0x1004238d3  sub     rdx, rbx
0x1004238d6  mov     rax, r12
0x1004238d9  cmp     rcx, rbx
0x1004238dc  cmovnb  rax, rdx
0x1004238e0  add     [rbp+0C78h], rax
0x1004238e7  mov     [rsp+88h+var_58], 1
0x1004238ef  movzx   eax, byte ptr [rsi+3128h]
0x1004238f6  test    al, al
0x1004238f8  jnz     short loc_100423968
0x1004238fa  mov     [rsi+3110h], r12
0x100423901  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100423908  cmp     dword ptr [rax], 0
0x10042390b  jz      short loc_100423925
0x10042390d  lea     rcx, [rsp+88h+arg_18]; lpPerformanceCount
0x100423915  call    cs:__imp_QueryPerformanceCounter
0x10042391b  mov     rax, qword ptr [rsp+88h+arg_18]
0x100423923  jmp     short loc_10042392D
0x100423925  mov     rax, ds:7FFE0008h
0x10042392d  mov     r8, [rdi+8]
0x100423931  mov     rdx, r8
0x100423934  sub     rdx, rax
0x100423937  js      short loc_100423945
0x100423939  mov     rcx, r12
0x10042393c  cmp     r8, rax
0x10042393f  cmovnb  rcx, rdx
0x100423943  jmp     short loc_10042395C
0x100423945  mov     byte ptr [rsi+3128h], 1
0x10042394c  mov     rcx, [rsi+3148h]
0x100423953  mov     rax, [rcx]
0x100423956  call    qword ptr [rax+58h]
0x100423959  mov     rcx, r12
0x10042395c  mov     [rsi+3120h], rcx
0x100423963  lock dec word ptr [rdi+18h]
0x100423968  mov     rbx, [rsp+88h+var_60]
0x10042396d  test    rbx, rbx
0x100423970  jz      short loc_1004239B9
0x100423972  cmp     [rsp+88h+var_58], 0
0x100423977  jz      short loc_1004239B9
0x100423979  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x100423980  cmp     byte ptr [rax], 0
0x100423983  jz      short loc_1004239AC
0x100423985  call    cs:__imp_rand
0x10042398b  mov     r8d, eax
0x10042398e  mov     eax, 66666667h
0x100423993  imul    r8d
0x100423996  sar     edx, 1
0x100423998  mov     ecx, edx
0x10042399a  shr     ecx, 1Fh
0x10042399d  add     edx, ecx
0x10042399f  lea     ecx, [rdx+rdx*4]
0x1004239a2  cmp     r8d, ecx
0x1004239a5  jnz     short loc_1004239AC
0x1004239a7  call    ?UpdateStatSnapshot@?$Spinlock@$0PK@$02$0BAC@@@AEAAXXZ; Spinlock<250,3,258>::UpdateStatSnapshot(void)
0x1004239ac  mov     [rbx], r12
0x1004239af  mov     [rsp+88h+var_60], r12
0x1004239b4  mov     [rsp+88h+var_58], r12d
0x1004239b9  mov     eax, 0FFFFFFFFh
0x1004239be  lock xadd [rdi+18h], ax
0x1004239c4  cmp     ax, 1
0x1004239c8  jnz     short loc_100423A25
0x1004239ca  mov     [rsi+3110h], r12
0x1004239d1  mov     [rdi], r12
0x1004239d4  mov     r8, cs:?g_pReadTimeoutBlockHead@@3PEAVSNI_ReadTimeoutListBlock@@EA; SNI_ReadTimeoutListBlock * g_pReadTimeoutBlockHead
0x1004239db  mov     r9, 6666666666666667h; wchar_t *
0x1004239e5  lea     rax, [r8+10h]
0x1004239e9  cmp     rdi, rax
0x1004239ec  jb      short loc_100423A15
0x1004239ee  mov     rcx, rdi
0x1004239f1  sub     rcx, r8
0x1004239f4  sub     rcx, 10h
0x1004239f8  mov     rax, r9
0x1004239fb  imul    rcx
0x1004239fe  sar     rdx, 4
0x100423a02  mov     rax, rdx
0x100423a05  shr     rax, 3Fh
0x100423a09  add     rdx, rax
0x100423a0c  cmp     rdx, 1FE0h
0x100423a13  jb      short loc_100423A1F
0x100423a15  mov     r8, [r8]
0x100423a18  test    r8, r8
0x100423a1b  jz      short loc_100423A25
0x100423a1d  jmp     short loc_1004239E5
0x100423a1f  lock dec word ptr [r8+8]
0x100423a25  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100423a2c  jz      short loc_100423A42
0x100423a2e  mov     r8d, [rsp+88h+var_40]; int
0x100423a33  mov     rdx, [rsp+88h+var_48]; char *
0x100423a38  mov     rcx, [rsp+88h+var_50]; char *
0x100423a3d  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x100423a42  add     rsp, 50h
0x100423a46  pop     r15
0x100423a48  pop     r14
0x100423a4a  pop     r12
0x100423a4c  pop     rdi
0x100423a4d  pop     rsi
0x100423a4e  pop     rbp
0x100423a4f  pop     rbx
0x100423a50  retn
```
