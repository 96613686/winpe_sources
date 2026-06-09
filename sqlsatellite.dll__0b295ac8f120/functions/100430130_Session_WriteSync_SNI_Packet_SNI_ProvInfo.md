# Session::WriteSync(SNI_Packet *,SNI_ProvInfo *)

- ea: `0x100430130`
- end: `0x1004306ea`
- name: `?WriteSync@Session@@UEAAKPEAVSNI_Packet@@PEAUSNI_ProvInfo@@@Z`
- size: `1466`
- prototype: `unsigned int __fastcall(Session *__hidden this, struct SNI_Packet *, struct SNI_ProvInfo *)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x10041d520`
- `0x10041d950`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x10042c7f0`
- `0x10042f1d0`
- `0x10042f360`
- `0x100430130`
- `0x100433440`
- `0x100433a70`
- `0x1004349f0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x10043028c`
- `KERNEL32!WaitForSingleObject` at `0x10043028c`
- `KERNEL32!GetLastError` at `0x1004302a2`
- `KERNEL32!GetLastError` at `0x1004302a2`

## string_xrefs

- `0x100430207`: `Worker access incremented; new value = %d\n`
- `0x10043021b`: `sql\common\dk\sni\include\smux.hpp`
- `0x10043038f`: `sql\common\dk\sni\include\smux.hpp`
- `0x100430214`: `Smux::IncrementWorkerAccessCounter`
- `0x100430388`: `Smux::DecrementWorkerAccessCounter`
- `0x10043037b`: `Worker access decremented; new value = %d\n`
- `0x10043015e`: `sql\common\dk\sni\src\smux.cpp`
- `0x100430169`: `Session::WriteSync`
- `0x100430535`: `Session::WriteSync`
- `0x100430577`: `Session::WriteSync`
- `0x100430616`: `Session::WriteSync`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Session::WriteSync(Session *this, struct SNI_Packet *a2, struct SNI_ProvInfo *a3)
{
  char v5; // al
  char v6; // cl
  __int64 v7; // rbx
  signed __int32 v8; // eax
  SOS_UnfairRecursiveMutexExtendedGuarantee **v9; // rbx
  __int64 v10; // rcx
  DWORD v11; // eax
  DWORD LastError; // esi
  unsigned int v13; // edx
  char v14; // bl
  const wchar_t *v15; // r9
  signed __int32 v16; // r15d
  Smux *v17; // rbp
  char v18; // bl
  char v19; // al
  SOS_UnfairRecursiveMutexExtendedGuarantee **v20; // rbx
  bool v21; // cf
  SOS_UnfairRecursiveMutexExtendedGuarantee **v23; // rbx
  __int64 v24; // [rsp+20h] [rbp-A8h]
  void *v25; // [rsp+28h] [rbp-A0h]
  void *v26; // [rsp+28h] [rbp-A0h]
  unsigned int *v27; // [rsp+30h] [rbp-98h]
  unsigned int *v28; // [rsp+30h] [rbp-98h]

  v5 = g_XeSniPkg_enabledBitmap;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
  {
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\smux.cpp",
      "Session::WriteSync",
      2458,
      L"API|SNI%u#, pPacket: %p{SNI_Packet*}, pProvInfo: %p{SNI_ProvInfo*}\n",
      *((_DWORD *)this + 11),
      a2,
      a3);
    v5 = g_XeSniPkg_enabledBitmap;
  }
  v6 = *((_BYTE *)this + 161);
  if ( v6 || *((_BYTE *)this + 163) || *((_BYTE *)this + 164) )
  {
    LastError = -1;
    if ( (v5 & 2) != 0 )
    {
      LODWORD(v27) = -1;
      LODWORD(v25) = 19 - (v6 != 0);
      LODWORD(v24) = 2;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\smux.cpp",
        "Session::WriteSync",
        2468,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        v24,
        v25,
        v27);
      v6 = *((_BYTE *)this + 161);
    }
    SNISetLastError(2u, 0xFFFFFFFF, 50119 - (v6 != 0));
  }
  else
  {
    while ( 1 )
    {
      if ( *((_DWORD *)this + 17) != *((_DWORD *)this + 18) )
      {
        v23 = (SOS_UnfairRecursiveMutexExtendedGuarantee **)*((_QWORD *)this + 7);
        CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v23);
        LastError = Session::SendDataPacket(this, a2, 1);
        SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v23[1]);
        if ( LastError == 997 )
          LastError = Session::WaitForSendDataPacketToComplete(this, a2);
        *((_DWORD *)a2 + 44) -= 16;
        *((_DWORD *)a2 + 46) += 16;
        goto LABEL_53;
      }
      v7 = *((_QWORD *)this + 6);
      v8 = _InterlockedIncrement((volatile signed __int32 *)(v7 + 124));
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(v24) = v8;
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\include\\smux.hpp",
          "Smux::IncrementWorkerAccessCounter",
          96,
          L"Worker access incremented; new value = %d\n",
          v24);
      }
      if ( !_InterlockedCompareExchange64((volatile signed __int64 *)(v7 + 136), (signed __int64)this, 0) )
        break;
      v9 = (SOS_UnfairRecursiveMutexExtendedGuarantee **)*((_QWORD *)this + 7);
      CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v9);
      if ( *((_DWORD *)this + 17) != *((_DWORD *)this + 18) )
      {
        v16 = _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)this + 6) + 124LL));
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          LODWORD(v24) = v16;
          SNIXE_SNI_TRACE_ON(
            "sql\\common\\dk\\sni\\include\\smux.hpp",
            "Smux::DecrementWorkerAccessCounter",
            113,
            L"Worker access decremented; new value = %d\n",
            v24);
        }
        LastError = Session::SendDataPacket(this, a2, 1);
        SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v9[1]);
        if ( LastError == 997 )
          LastError = Session::WaitForSendDataPacketToComplete(this, a2);
        *((_DWORD *)a2 + 44) -= 16;
        *((_DWORD *)a2 + 46) += 16;
        goto LABEL_53;
      }
      *((_BYTE *)this + 201) = 1;
      v10 = *((_QWORD *)this + 23);
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 24LL))(v10);
      v11 = WaitForSingleObject(*((HANDLE *)this + 24), 0xFFFFFFFF);
      if ( v11 )
      {
        if ( v11 == 258 )
        {
          v13 = 258;
          LastError = 258;
          goto LABEL_22;
        }
        if ( v11 != -1 )
        {
          LastError = -2147418113;
          v13 = -2147418113;
LABEL_22:
          Session::HandleWaitError(this, v13);
          goto LABEL_53;
        }
        LastError = GetLastError();
        v13 = LastError;
        if ( LastError )
          goto LABEL_22;
      }
      v14 = *((_BYTE *)this + 161);
      if ( v14 || *((_BYTE *)this + 163) )
      {
        if ( *((_DWORD *)this + 17) == *((_DWORD *)this + 18) )
          Smux::WakeUpNextWorker(*((Smux **)this + 6), 0, 0);
        LastError = -1;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(v27) = -1;
          LODWORD(v25) = 19 - (v14 != 0);
          LODWORD(v24) = 2;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\smux.cpp",
            "Session::WriteSync",
            2615,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            v24,
            v25,
            v27);
        }
        SNISetLastError(2u, 0xFFFFFFFF, 50119 - (v14 != 0));
        goto LABEL_53;
      }
    }
    v17 = (Smux *)*((_QWORD *)this + 6);
    v18 = *((_BYTE *)this + 161);
    if ( v18 || *((_BYTE *)this + 163) || *((_BYTE *)this + 164) )
    {
      LastError = -1;
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v27) = -1;
        LODWORD(v25) = 19 - (v18 != 0);
        LODWORD(v24) = 2;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\smux.cpp",
          "Session::WriteSync",
          2506,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          v24,
          v25,
          v27);
      }
      v21 = v18 != 0;
LABEL_50:
      SNISetLastError(2u, 0xFFFFFFFF, 50119 - v21);
    }
    else if ( *((_DWORD *)this + 17) == *((_DWORD *)this + 18) )
    {
      while ( 1 )
      {
        LastError = Smux::Worker(*((Smux **)this + 6), -1, 0, 0, 1, 0, 0);
        if ( LastError )
          break;
        v19 = *((_BYTE *)this + 161);
        if ( v19 || *((_BYTE *)this + 163) || *((_BYTE *)this + 164) )
        {
          LastError = -1;
          if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
          {
            LODWORD(v28) = -1;
            LODWORD(v26) = 19 - (v19 != 0);
            LODWORD(v24) = 2;
            SNIXE_SNI_ERROR_ON(
              "sql\\common\\dk\\sni\\src\\smux.cpp",
              "Session::WriteSync",
              2526,
              L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
              v24,
              v26,
              v28);
            v19 = *((_BYTE *)this + 161);
          }
          v21 = v19 != 0;
          goto LABEL_50;
        }
        if ( *((_DWORD *)this + 17) != *((_DWORD *)this + 18) )
          goto LABEL_42;
      }
    }
    else
    {
LABEL_42:
      if ( v17 )
      {
        Smux::WakeUpNextWorker(v17, this, 0);
        v17 = 0;
      }
      v20 = (SOS_UnfairRecursiveMutexExtendedGuarantee **)*((_QWORD *)this + 7);
      CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v20);
      LastError = Session::SendDataPacket(this, a2, 1);
      SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v20[1]);
      if ( LastError == 997 )
        LastError = Session::WaitForSendDataPacketToComplete(this, a2);
      *((_DWORD *)a2 + 44) -= 16;
      *((_DWORD *)a2 + 46) += 16;
    }
    if ( v17 )
      Smux::WakeUpNextWorker(v17, this, 0);
  }
LABEL_53:
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v24) = LastError;
    SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\smux.cpp", "Session::WriteSync", 2623, L"RET|SNI%d{WINERR}\n", v24);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\smux.cpp", "Session::WriteSync", 2458, v15);
  return LastError;
}

```

## disassembly

```asm
0x100430130  mov     rax, rsp
0x100430133  push    rdi
0x100430134  push    r12
0x100430136  push    r13
0x100430138  push    r14
0x10043013a  push    r15
0x10043013c  sub     rsp, 0A0h
0x100430143  mov     [rsp+0C8h+var_88], 0FFFFFFFFFFFFFFFEh
0x10043014c  mov     [rax+8], rbx
0x100430150  mov     [rax+10h], rbp
0x100430154  mov     [rax+18h], rsi
0x100430158  mov     r14, rdx
0x10043015b  mov     rdi, rcx
0x10043015e  lea     r13, aSqlCommonDkSni_12; "sql\\common\\dk\\sni\\src\\smux.cpp"
0x100430165  mov     [rax-48h], r13
0x100430169  lea     rbp, aSessionWritesy; "Session::WriteSync"
0x100430170  mov     [rax-40h], rbp
0x100430174  mov     dword ptr [rax-38h], 99Ah
0x10043017b  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100430181  test    al, 40h
0x100430183  jz      short loc_1004301B4
0x100430185  mov     [rsp+0C8h+var_98], r8
0x10043018a  mov     [rsp+0C8h+var_A0], rdx
0x10043018f  mov     eax, [rcx+2Ch]
0x100430192  mov     dword ptr [rsp+0C8h+var_A8], eax
0x100430196  lea     r9, aApiSniUPpacket; "API|SNI%u#, pPacket: %p{SNI_Packet*}, p"...
0x10043019d  mov     r8d, 99Ah; int
0x1004301a3  mov     rdx, rbp; char *
0x1004301a6  mov     rcx, r13; char *
0x1004301a9  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x1004301ae  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004301b4  movzx   ecx, byte ptr [rdi+0A1h]
0x1004301bb  test    cl, cl
0x1004301bd  jnz     loc_10043068D
0x1004301c3  cmp     [rdi+0A3h], cl
0x1004301c9  jnz     loc_10043068D
0x1004301cf  cmp     [rdi+0A4h], cl
0x1004301d5  jnz     loc_10043068D
0x1004301db  xor     r12d, r12d
0x1004301de  mov     eax, [rdi+48h]
0x1004301e1  cmp     [rdi+44h], eax
0x1004301e4  jnz     loc_10043062C
0x1004301ea  mov     rbx, [rdi+30h]
0x1004301ee  mov     eax, 1
0x1004301f3  lock xadd [rbx+7Ch], eax
0x1004301f8  inc     eax
0x1004301fa  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100430201  jz      short loc_100430227
0x100430203  mov     dword ptr [rsp+0C8h+var_A8], eax
0x100430207  lea     r9, aWorkerAccessIn; "Worker access incremented; new value = "...
0x10043020e  mov     r8d, 60h ; '`'; int
0x100430214  lea     rdx, aSmuxIncrementw; "Smux::IncrementWorkerAccessCounter"
0x10043021b  lea     rcx, aSqlCommonDkSni; "sql\\common\\dk\\sni\\include\\smux.hpp"
0x100430222  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100430227  xor     eax, eax
0x100430229  lock cmpxchg [rbx+88h], rdi
0x100430232  jz      loc_1004303E3
0x100430238  mov     rbx, [rdi+38h]
0x10043023c  mov     [rsp+0C8h+var_80], rbx
0x100430241  mov     [rsp+0C8h+var_78], r12d
0x100430246  mov     rcx, rbx; this
0x100430249  call    ?Enter@CCriticalSectionSOS@@QEAAXXZ; CCriticalSectionSOS::Enter(void)
0x10043024e  mov     [rsp+0C8h+var_78], 1
0x100430256  mov     eax, [rdi+48h]
0x100430259  cmp     [rdi+44h], eax
0x10043025c  jnz     loc_10043035A
0x100430262  mov     byte ptr [rdi+0C9h], 1
0x100430269  mov     [rsp+0C8h+var_78], r12d
0x10043026e  mov     rcx, [rdi+0B8h]
0x100430275  test    rcx, rcx
0x100430278  jz      short loc_100430280
0x10043027a  mov     rax, [rcx]
0x10043027d  call    qword ptr [rax+18h]
0x100430280  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x100430285  mov     rcx, [rdi+0C0h]; hHandle
0x10043028c  call    cs:__imp_WaitForSingleObject
0x100430292  test    eax, eax
0x100430294  jz      short loc_1004302B0
0x100430296  cmp     eax, 102h
0x10043029b  jz      short loc_1004302D1
0x10043029d  cmp     eax, 0FFFFFFFFh
0x1004302a0  jnz     short loc_1004302C8
0x1004302a2  call    cs:__imp_GetLastError
0x1004302a8  mov     esi, eax
0x1004302aa  mov     edx, eax
0x1004302ac  test    eax, eax
0x1004302ae  jnz     short loc_1004302D8
0x1004302b0  movzx   ebx, byte ptr [rdi+0A1h]
0x1004302b7  test    bl, bl
0x1004302b9  jnz     short loc_1004302E6
0x1004302bb  cmp     [rdi+0A3h], bl
0x1004302c1  jnz     short loc_1004302E6
0x1004302c3  jmp     loc_1004301DE
0x1004302c8  mov     esi, 8000FFFFh
0x1004302cd  mov     edx, esi
0x1004302cf  jmp     short loc_1004302D8
0x1004302d1  mov     edx, 102h; unsigned int
0x1004302d6  mov     esi, edx
0x1004302d8  mov     rcx, rdi; this
0x1004302db  call    ?HandleWaitError@Session@@AEAAXK@Z; Session::HandleWaitError(ulong)
0x1004302e0  nop
0x1004302e1  jmp     loc_10043057E
0x1004302e6  mov     eax, [rdi+48h]
0x1004302e9  cmp     [rdi+44h], eax
0x1004302ec  jnz     short loc_1004302FC
0x1004302ee  xor     r8d, r8d; bool
0x1004302f1  xor     edx, edx; struct Session *
0x1004302f3  mov     rcx, [rdi+30h]; this
0x1004302f7  call    ?WakeUpNextWorker@Smux@@QEAAXPEAVSession@@_N@Z; Smux::WakeUpNextWorker(Session *,bool)
0x1004302fc  mov     esi, 0FFFFFFFFh
0x100430301  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100430308  jz      short loc_10043033C
0x10043030a  movzx   eax, bl
0x10043030d  neg     al
0x10043030f  sbb     ecx, ecx
0x100430311  add     ecx, 13h
0x100430314  mov     dword ptr [rsp+0C8h+var_98], esi
0x100430318  mov     dword ptr [rsp+0C8h+var_A0], ecx
0x10043031c  mov     dword ptr [rsp+0C8h+var_A8], 2
0x100430324  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10043032b  mov     r8d, 0A37h; int
0x100430331  mov     rdx, rbp; char *
0x100430334  mov     rcx, r13; char *
0x100430337  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043033c  neg     bl
0x10043033e  sbb     r8d, r8d
0x100430341  add     r8d, 0C3C7h
0x100430348  mov     edx, esi
0x10043034a  mov     ecx, 2
0x10043034f  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100430354  nop
0x100430355  jmp     loc_10043057E
0x10043035a  mov     rax, [rdi+30h]
0x10043035e  mov     r15d, 0FFFFFFFFh
0x100430364  lock xadd [rax+7Ch], r15d
0x10043036a  dec     r15d
0x10043036d  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100430374  jz      short loc_10043039B
0x100430376  mov     dword ptr [rsp+0C8h+var_A8], r15d
0x10043037b  lea     r9, aWorkerAccessDe; "Worker access decremented; new value = "...
0x100430382  mov     r8d, 71h ; 'q'; int
0x100430388  lea     rdx, aSmuxDecrementw; "Smux::DecrementWorkerAccessCounter"
0x10043038f  lea     rcx, aSqlCommonDkSni; "sql\\common\\dk\\sni\\include\\smux.hpp"
0x100430396  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043039b  mov     r8b, 1; bool
0x10043039e  mov     rdx, r14; struct SNI_Packet *
0x1004303a1  mov     rcx, rdi; this
0x1004303a4  call    ?SendDataPacket@Session@@AEAAKPEAVSNI_Packet@@_N@Z; Session::SendDataPacket(SNI_Packet *,bool)
0x1004303a9  mov     esi, eax
0x1004303ab  mov     rcx, [rbx+8]; this
0x1004303af  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x1004303b4  mov     [rsp+0C8h+var_78], r12d
0x1004303b9  cmp     esi, 3E5h
0x1004303bf  jnz     short loc_1004303CE
0x1004303c1  mov     rdx, r14; struct SNI_Packet *
0x1004303c4  mov     rcx, rdi; this
0x1004303c7  call    ?WaitForSendDataPacketToComplete@Session@@AEAAKPEAVSNI_Packet@@@Z; Session::WaitForSendDataPacketToComplete(SNI_Packet *)
0x1004303cc  mov     esi, eax
0x1004303ce  add     dword ptr [r14+0B0h], 0FFFFFFF0h
0x1004303d6  add     dword ptr [r14+0B8h], 10h
0x1004303de  jmp     loc_10043057E
0x1004303e3  mov     rbp, [rdi+30h]
0x1004303e7  mov     [rsp+0C8h+var_60], rbp
0x1004303ec  mov     [rsp+0C8h+var_58], rdi
0x1004303f1  mov     [rsp+0C8h+var_50], 0
0x1004303f6  movzx   ebx, byte ptr [rdi+0A1h]
0x1004303fd  test    bl, bl
0x1004303ff  jnz     loc_1004305E1
0x100430405  cmp     [rdi+0A3h], bl
0x10043040b  jnz     loc_1004305E1
0x100430411  cmp     [rdi+0A4h], bl
0x100430417  jnz     loc_1004305E1
0x10043041d  mov     eax, [rdi+48h]
0x100430420  cmp     [rdi+44h], eax
0x100430423  jnz     short loc_10043048A
0x100430425  mov     r15d, 0FFFFFFFFh
0x10043042b  nop     dword ptr [rax+rax+00h]
0x100430430  xor     r9d, r9d; unsigned __int16
0x100430433  mov     [rsp+0C8h+var_98], r12; unsigned int *
0x100430438  mov     [rsp+0C8h+var_A0], r12; void *
0x10043043d  mov     [rsp+0C8h+var_A8], 1; bool
0x100430442  xor     r8d, r8d; struct SNI_Packet **
0x100430445  mov     edx, r15d; int
0x100430448  mov     rcx, [rdi+30h]; this
0x10043044c  call    ?Worker@Smux@@QEAAKHPEAPEAVSNI_Packet@@G_NPEAXPEAK@Z; Smux::Worker(int,SNI_Packet * *,ushort,bool,void *,ulong *)
0x100430451  mov     esi, eax
0x100430453  test    eax, eax
0x100430455  jnz     loc_100430564
0x10043045b  movzx   eax, byte ptr [rdi+0A1h]
0x100430462  test    al, al
0x100430464  jnz     loc_100430503
0x10043046a  cmp     [rdi+0A3h], al
0x100430470  jnz     loc_100430503
0x100430476  cmp     [rdi+0A4h], al
0x10043047c  jnz     loc_100430503
0x100430482  mov     eax, [rdi+48h]
0x100430485  cmp     [rdi+44h], eax
0x100430488  jz      short loc_100430430
0x10043048a  test    rbp, rbp
0x10043048d  jz      short loc_1004304A5
0x10043048f  xor     r8d, r8d; bool
0x100430492  mov     rdx, rdi; struct Session *
0x100430495  mov     rcx, rbp; this
0x100430498  call    ?WakeUpNextWorker@Smux@@QEAAXPEAVSession@@_N@Z; Smux::WakeUpNextWorker(Session *,bool)
0x10043049d  mov     rbp, r12
0x1004304a0  mov     [rsp+0C8h+var_60], r12
0x1004304a5  mov     rbx, [rdi+38h]
0x1004304a9  mov     [rsp+0C8h+var_70], rbx
0x1004304ae  mov     [rsp+0C8h+var_68], r12d
0x1004304b3  mov     rcx, rbx; this
0x1004304b6  call    ?Enter@CCriticalSectionSOS@@QEAAXXZ; CCriticalSectionSOS::Enter(void)
0x1004304bb  mov     [rsp+0C8h+var_68], 1
0x1004304c3  mov     r8b, 1; bool
0x1004304c6  mov     rdx, r14; struct SNI_Packet *
0x1004304c9  mov     rcx, rdi; this
0x1004304cc  call    ?SendDataPacket@Session@@AEAAKPEAVSNI_Packet@@_N@Z; Session::SendDataPacket(SNI_Packet *,bool)
0x1004304d1  mov     esi, eax
0x1004304d3  mov     rcx, [rbx+8]; this
0x1004304d7  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x1004304dc  cmp     esi, 3E5h
0x1004304e2  jnz     short loc_1004304F1
0x1004304e4  mov     rdx, r14; struct SNI_Packet *
0x1004304e7  mov     rcx, rdi; this
0x1004304ea  call    ?WaitForSendDataPacketToComplete@Session@@AEAAKPEAVSNI_Packet@@@Z; Session::WaitForSendDataPacketToComplete(SNI_Packet *)
0x1004304ef  mov     esi, eax
0x1004304f1  add     dword ptr [r14+0B0h], 0FFFFFFF0h
0x1004304f9  add     dword ptr [r14+0B8h], 10h
0x100430501  jmp     short loc_100430564
0x100430503  mov     esi, 0FFFFFFFFh
0x100430508  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043050f  jz      short loc_10043054B
0x100430511  neg     al
0x100430513  sbb     eax, eax
0x100430515  add     eax, 13h
0x100430518  mov     dword ptr [rsp+0C8h+var_98], esi
0x10043051c  mov     dword ptr [rsp+0C8h+var_A0], eax
0x100430520  mov     dword ptr [rsp+0C8h+var_A8], 2
0x100430528  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10043052f  mov     r8d, 9DEh; int
0x100430535  lea     rdx, aSessionWritesy; "Session::WriteSync"
0x10043053c  mov     rcx, r13; char *
0x10043053f  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100430544  movzx   eax, byte ptr [rdi+0A1h]
0x10043054b  neg     al
0x10043054d  sbb     r8d, r8d
0x100430550  add     r8d, 0C3C7h
0x100430557  mov     edx, esi
0x100430559  mov     ecx, 2
0x10043055e  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100430563  nop
0x100430564  test    rbp, rbp
0x100430567  jz      short loc_100430577
0x100430569  xor     r8d, r8d; bool
0x10043056c  mov     rdx, rdi; struct Session *
0x10043056f  mov     rcx, rbp; this
0x100430572  call    ?WakeUpNextWorker@Smux@@QEAAXPEAVSession@@_N@Z; Smux::WakeUpNextWorker(Session *,bool)
0x100430577  lea     rbp, aSessionWritesy; "Session::WriteSync"
0x10043057e  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100430585  jz      short loc_1004305A4
0x100430587  mov     dword ptr [rsp+0C8h+var_A8], esi
0x10043058b  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100430592  mov     r8d, 0A3Fh; int
0x100430598  mov     rdx, rbp; char *
0x10043059b  mov     rcx, r13; char *
0x10043059e  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x1004305a3  nop
0x1004305a4  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004305ab  jz      short loc_1004305BE
0x1004305ad  mov     r8d, 99Ah; int
0x1004305b3  mov     rdx, rbp; char *
0x1004305b6  mov     rcx, r13; char *
0x1004305b9  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x1004305be  mov     eax, esi
0x1004305c0  lea     r11, [rsp+0C8h+var_28]
0x1004305c8  mov     rbx, [r11+30h]
0x1004305cc  mov     rbp, [r11+38h]
0x1004305d0  mov     rsi, [r11+40h]
0x1004305d4  mov     rsp, r11
0x1004305d7  pop     r15
0x1004305d9  pop     r14
0x1004305db  pop     r13
0x1004305dd  pop     r12
0x1004305df  pop     rdi
0x1004305e0  retn
0x1004305e1  mov     esi, 0FFFFFFFFh
0x1004305e6  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004305ed  jz      short loc_100430625
0x1004305ef  movzx   eax, bl
0x1004305f2  neg     al
0x1004305f4  sbb     ecx, ecx
0x1004305f6  add     ecx, 13h
0x1004305f9  mov     dword ptr [rsp+0C8h+var_98], esi
0x1004305fd  mov     dword ptr [rsp+0C8h+var_A0], ecx
0x100430601  mov     dword ptr [rsp+0C8h+var_A8], 2
0x100430609  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100430610  mov     r8d, 9CAh; int
0x100430616  lea     rdx, aSessionWritesy; "Session::WriteSync"
0x10043061d  mov     rcx, r13; char *
0x100430620  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100430625  neg     bl
  ... truncated ...
```
