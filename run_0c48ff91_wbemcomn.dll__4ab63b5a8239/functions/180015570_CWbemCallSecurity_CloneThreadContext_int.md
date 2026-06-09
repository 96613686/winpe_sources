# CWbemCallSecurity::CloneThreadContext(int)

- ea: `0x180015570`
- end: `0x1800159f0`
- name: `?CloneThreadContext@CWbemCallSecurity@@UEAAJH@Z`
- size: `1152`
- prototype: `__int64 __fastcall(CWbemCallSecurity *__hidden this, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180013564`
- `0x180014120`
- `0x1800154d0`
- `0x180015570`
- `0x180015a00`
- `0x1800280c0`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800155a4`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800155a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015713`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015713`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWbemCallSecurity::CloneThreadContext(CWbemCallSecurity *this, int a2)
{
  HRESULT v4; // eax
  void *v5; // rbx
  __int64 v6; // rdi
  unsigned int v7; // r14d
  int v9; // r13d
  __int64 v10; // rax
  unsigned __int64 v11; // rdi
  unsigned __int16 *v12; // rax
  int v13; // edi
  signed int v14; // eax
  unsigned int v15; // edi
  unsigned int v16; // edi
  void *v17; // [rsp+50h] [rbp-58h]
  __int64 v18; // [rsp+58h] [rbp-50h] BYREF
  __int64 v19; // [rsp+60h] [rbp-48h]
  unsigned __int16 *v20; // [rsp+68h] [rbp-40h] BYREF
  unsigned int v21; // [rsp+B0h] [rbp+8h] BYREF
  int v22; // [rsp+C0h] [rbp+18h] BYREF
  void *v23; // [rsp+C8h] [rbp+20h] BYREF

  if ( *((_QWORD *)this + 2) )
    return 2147500036LL;
  v23 = 0;
  v4 = CoGetCallContext(&IID_IServerSecurity, &v23);
  v5 = v23;
  v17 = v23;
  if ( v4 )
  {
    v16 = CWbemCallSecurity::CloneThreadToken(this, 6);
    if ( v5 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 16LL))(v5);
    return v16;
  }
  else
  {
    v18 = 0;
    if ( (**(int (__fastcall ***)(void *, GUID *, __int64 *))v23)(v23, &IID_IWbemCallSecurity, &v18) < 0 )
    {
      v20 = 0;
      v22 = 0;
      v9 = (*(__int64 (__fastcall **)(void *, char *, char *, char *, char *, int *, unsigned __int16 **, _QWORD))(*(_QWORD *)v23 + 24LL))(
             v23,
             (char *)this + 32,
             (char *)this + 36,
             (char *)this + 48,
             (char *)this + 40,
             &v22,
             &v20,
             0);
      if ( v9 < 0 )
      {
        v9 = (*(__int64 (__fastcall **)(void *, char *, char *, char *, char *, int *, _QWORD, _QWORD))(*(_QWORD *)v23 + 24LL))(
               v23,
               (char *)this + 32,
               (char *)this + 36,
               (char *)this + 48,
               (char *)this + 40,
               &v22,
               0,
               0);
        v20 = 0;
        if ( v9 < 0 )
        {
          *((_DWORD *)this + 6) = 0;
          if ( v5 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 16LL))(v5);
          return 0;
        }
      }
      else if ( v20 )
      {
        v10 = -1;
        do
          ++v10;
        while ( v20[v10] );
        v11 = v10 + 1;
        v12 = (unsigned __int16 *)CoTaskMemAlloc(2 * (v10 + 1));
        *((_QWORD *)this + 7) = v12;
        if ( v12 )
        {
          v14 = StringCchCopyW(v12, v11, v20);
          v15 = v14;
          if ( v14 < 0 )
          {
            CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v14);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_b9e966f598bb3ae9dbe33aa859f4cbf6_Traceguids, v15);
            }
          }
        }
      }
      v13 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v23 + 48LL))(v23);
      if ( !v13 )
        v9 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v23 + 32LL))(v23);
      if ( v9 >= 0 )
      {
        v7 = CWbemCallSecurity::CloneThreadToken(this, *((_DWORD *)this + 10));
        if ( !v13 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v23 + 40LL))(v23);
        if ( v7 != -2147217406 )
        {
          if ( (v7 & 0x80000000) != 0 )
            CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v7);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_b9e966f598bb3ae9dbe33aa859f4cbf6_Traceguids, v7);
          }
          goto LABEL_8;
        }
        if ( v5 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 16LL))(v5);
        return 2147749890LL;
      }
      else
      {
        if ( !v13 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v23 + 40LL))(v23);
        if ( v5 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 16LL))(v5);
        return 2147500037LL;
      }
    }
    else
    {
      v6 = v18;
      v19 = v18;
      if ( !a2 )
      {
        v21 = 0;
        (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, unsigned int *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v18 + 24LL))(
          v18,
          0,
          0,
          0,
          &v21,
          0,
          0,
          0);
        v7 = CWbemCallSecurity::CloneThreadToken(this, v21);
        if ( v6 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        v19 = 0;
LABEL_8:
        if ( v5 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 16LL))(v5);
        return v7;
      }
      try
      {
        CWbemCallSecurity::operator=(this, v18);
      }
      catch ( CX_Exception )
      {
        if ( v19 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        v19 = 0;
        if ( v17 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v17 + 16LL))(v17);
        return 2147749894LL;
      }
      if ( v6 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      v19 = 0;
      if ( v5 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 16LL))(v5);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x180015570  mov     rax, rsp
0x180015573  push    rbx
0x180015574  push    rsi
0x180015575  push    rdi
0x180015576  push    r12
0x180015578  push    r13
0x18001557a  push    r14
0x18001557c  push    r15
0x18001557e  sub     rsp, 70h
0x180015582  mov     r15d, edx
0x180015585  mov     r14, rcx
0x180015588  cmp     qword ptr [rcx+10h], 0
0x18001558d  jnz     loc_18001599A
0x180015593  xor     esi, esi
0x180015595  mov     [rax+20h], rsi
0x180015599  lea     rdx, [rax+20h]; ppInterface
0x18001559d  lea     rcx, IID_IServerSecurity; riid
0x1800155a4  call    cs:__imp_CoGetCallContext
0x1800155aa  mov     rbx, [rsp+0A8h+arg_18]
0x1800155b2  mov     [rsp+0A8h+var_58], rbx
0x1800155b7  test    eax, eax
0x1800155b9  jnz     loc_180015895
0x1800155bf  mov     [rsp+0A8h+var_50], rsi
0x1800155c4  mov     rcx, [rsp+0A8h+arg_18]
0x1800155cc  mov     rax, [rcx]
0x1800155cf  lea     r8, [rsp+0A8h+var_50]
0x1800155d4  lea     rdx, IID_IWbemCallSecurity
0x1800155db  mov     rax, [rax]
0x1800155de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155e3  test    eax, eax
0x1800155e5  js      loc_180015691
0x1800155eb  mov     rdi, [rsp+0A8h+var_50]
0x1800155f0  mov     [rsp+0A8h+var_48], rdi
0x1800155f5  test    r15d, r15d
0x1800155f8  jnz     loc_1800159A4
0x1800155fe  mov     [rsp+0A8h+arg_0], esi
0x180015605  mov     rcx, [rsp+0A8h+var_50]
0x18001560a  mov     rax, [rcx]
0x18001560d  mov     [rsp+0A8h+var_70], rsi
0x180015612  mov     [rsp+0A8h+var_78], rsi
0x180015617  mov     [rsp+0A8h+var_80], rsi
0x18001561c  lea     rdx, [rsp+0A8h+arg_0]
0x180015624  mov     [rsp+0A8h+var_88], rdx
0x180015629  xor     r9d, r9d
0x18001562c  xor     r8d, r8d
0x18001562f  xor     edx, edx
0x180015631  mov     rax, [rax+18h]
0x180015635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001563a  mov     edx, [rsp+0A8h+arg_0]; unsigned int
0x180015641  mov     rcx, r14; this
0x180015644  call    ?CloneThreadToken@CWbemCallSecurity@@AEAAJK@Z; CWbemCallSecurity::CloneThreadToken(ulong)
0x180015649  mov     r14d, eax
0x18001564c  test    rdi, rdi
0x18001564f  jz      short loc_180015660
0x180015651  mov     rcx, [rdi]
0x180015654  mov     rax, [rcx+10h]
0x180015658  mov     rcx, rdi
0x18001565b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015660  mov     [rsp+0A8h+var_48], rsi
0x180015665  test    rbx, rbx
0x180015668  jz      short loc_180015679
0x18001566a  mov     rax, [rbx]
0x18001566d  mov     rcx, rbx
0x180015670  mov     rax, [rax+10h]
0x180015674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015679  mov     eax, r14d
0x18001567c  mov     [rsp+0A8h+var_58], rsi
0x180015681  add     rsp, 70h
0x180015685  pop     r15
0x180015687  pop     r14
0x180015689  pop     r13
0x18001568b  pop     r12
0x18001568d  pop     rdi
0x18001568e  pop     rsi
0x18001568f  pop     rbx
0x180015690  retn
0x180015691  mov     [rsp+0A8h+var_40], rsi
0x180015696  mov     [rsp+0A8h+arg_10], esi
0x18001569d  lea     rdx, [r14+28h]
0x1800156a1  mov     rcx, [rsp+0A8h+arg_18]
0x1800156a9  mov     rax, [rcx]
0x1800156ac  mov     [rsp+0A8h+var_70], rsi
0x1800156b1  lea     r8, [rsp+0A8h+var_40]
0x1800156b6  mov     [rsp+0A8h+var_78], r8
0x1800156bb  lea     r8, [rsp+0A8h+arg_10]
0x1800156c3  mov     [rsp+0A8h+var_80], r8
0x1800156c8  mov     [rsp+0A8h+var_88], rdx
0x1800156cd  lea     r9, [r14+30h]
0x1800156d1  lea     r8, [r14+24h]
0x1800156d5  lea     rdx, [r14+20h]
0x1800156d9  mov     rax, [rax+18h]
0x1800156dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156e2  mov     r13d, eax
0x1800156e5  test    eax, eax
0x1800156e7  js      loc_1800158BF
0x1800156ed  mov     rcx, [rsp+0A8h+var_40]
0x1800156f2  test    rcx, rcx
0x1800156f5  jz      short loc_180015726
0x1800156f7  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800156fe  xchg    ax, ax
0x180015700  lea     rax, [rax+1]
0x180015704  cmp     word ptr [rcx+rax*2], 0
0x180015709  jnz     short loc_180015700
0x18001570b  lea     rdi, [rax+1]
0x18001570f  lea     rcx, [rdi+rdi]; cb
0x180015713  call    cs:__imp_CoTaskMemAlloc
0x180015719  mov     [r14+38h], rax
0x18001571d  test    rax, rax
0x180015720  jnz     loc_180015807
0x180015726  lea     r15, WPP_GLOBAL_Control
0x18001572d  mov     rcx, [rsp+0A8h+arg_18]
0x180015735  mov     rax, [rcx]
0x180015738  mov     rax, [rax+30h]
0x18001573c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015741  mov     edi, eax
0x180015743  test    eax, eax
0x180015745  jnz     short loc_18001575E
0x180015747  mov     rcx, [rsp+0A8h+arg_18]
0x18001574f  mov     rdx, [rcx]
0x180015752  mov     rax, [rdx+20h]
0x180015756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001575b  mov     r13d, eax
0x18001575e  test    r13d, r13d
0x180015761  jns     short loc_180015789
0x180015763  test    edi, edi
0x180015765  jz      loc_1800159C2
0x18001576b  test    rbx, rbx
0x18001576e  jz      short loc_18001577F
0x180015770  mov     rax, [rbx]
0x180015773  mov     rcx, rbx
0x180015776  mov     rax, [rax+10h]
0x18001577a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001577f  mov     eax, 80004005h
0x180015784  jmp     loc_18001567C
0x180015789  mov     edx, [r14+28h]; unsigned int
0x18001578d  mov     rcx, r14; this
0x180015790  call    ?CloneThreadToken@CWbemCallSecurity@@AEAAJK@Z; CWbemCallSecurity::CloneThreadToken(ulong)
0x180015795  mov     r14d, eax
0x180015798  test    edi, edi
0x18001579a  jnz     short loc_1800157B0
0x18001579c  mov     rcx, [rsp+0A8h+arg_18]
0x1800157a4  mov     rdx, [rcx]
0x1800157a7  mov     rax, [rdx+28h]
0x1800157ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157b0  cmp     r14d, 80041002h
0x1800157b7  jz      loc_180015877
0x1800157bd  test    r14d, r14d
0x1800157c0  js      loc_1800159DB
0x1800157c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800157cd  cmp     rcx, r15
0x1800157d0  jz      loc_180015665
0x1800157d6  test    byte ptr [rcx+1Ch], 1
0x1800157da  jz      loc_180015665
0x1800157e0  cmp     byte ptr [rcx+19h], 2
0x1800157e4  jb      loc_180015665
0x1800157ea  mov     edx, 11h
0x1800157ef  mov     r9d, r14d
0x1800157f2  lea     r8, WPP_b9e966f598bb3ae9dbe33aa859f4cbf6_Traceguids
0x1800157f9  mov     rcx, [rcx+10h]
0x1800157fd  call    WPP_SF_D
0x180015802  jmp     loc_180015665
0x180015807  mov     r8, [rsp+0A8h+var_40]; unsigned __int16 *
0x18001580c  mov     rdx, rdi; unsigned __int64
0x18001580f  mov     rcx, rax; unsigned __int16 *
0x180015812  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180015817  mov     edi, eax
0x180015819  test    eax, eax
0x18001581b  jns     loc_180015726
0x180015821  mov     edx, eax; int
0x180015823  lea     rcx, unk_18006A9C0; this
0x18001582a  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001582f  lea     r15, WPP_GLOBAL_Control
0x180015836  mov     rcx, cs:WPP_GLOBAL_Control
0x18001583d  cmp     rcx, r15
0x180015840  jz      loc_18001572D
0x180015846  test    byte ptr [rcx+1Ch], 1
0x18001584a  jz      loc_18001572D
0x180015850  cmp     byte ptr [rcx+19h], 2
0x180015854  jb      loc_18001572D
0x18001585a  mov     edx, 10h
0x18001585f  mov     r9d, edi
0x180015862  lea     r8, WPP_b9e966f598bb3ae9dbe33aa859f4cbf6_Traceguids
0x180015869  mov     rcx, [rcx+10h]
0x18001586d  call    WPP_SF_D
0x180015872  jmp     loc_18001572D
0x180015877  test    rbx, rbx
0x18001587a  jz      short loc_18001588B
0x18001587c  mov     rcx, [rbx]
0x18001587f  mov     rax, [rcx+10h]
0x180015883  mov     rcx, rbx
0x180015886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001588b  mov     eax, 80041002h
0x180015890  jmp     loc_18001567C
0x180015895  mov     edx, 6; unsigned int
0x18001589a  mov     rcx, r14; this
0x18001589d  call    ?CloneThreadToken@CWbemCallSecurity@@AEAAJK@Z; CWbemCallSecurity::CloneThreadToken(ulong)
0x1800158a2  mov     edi, eax
0x1800158a4  test    rbx, rbx
0x1800158a7  jz      short loc_1800158B8
0x1800158a9  mov     rcx, [rbx]
0x1800158ac  mov     rax, [rcx+10h]
0x1800158b0  mov     rcx, rbx
0x1800158b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158b8  mov     eax, edi
0x1800158ba  jmp     loc_18001567C
0x1800158bf  mov     rcx, [rsp+0A8h+arg_18]
0x1800158c7  mov     rax, [rcx]
0x1800158ca  mov     [rsp+0A8h+var_70], rsi
0x1800158cf  mov     [rsp+0A8h+var_78], rsi
0x1800158d4  lea     rdx, [rsp+0A8h+arg_10]
0x1800158dc  mov     [rsp+0A8h+var_80], rdx
0x1800158e1  lea     rdx, [r14+28h]
0x1800158e5  mov     [rsp+0A8h+var_88], rdx
0x1800158ea  lea     r9, [r14+30h]
0x1800158ee  lea     r8, [r14+24h]
0x1800158f2  lea     rdx, [r14+20h]
0x1800158f6  mov     rax, [rax+18h]
0x1800158fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158ff  mov     r13d, eax
0x180015902  mov     [rsp+0A8h+var_40], rsi
0x180015907  test    eax, eax
0x180015909  jns     loc_180015726
0x18001590f  mov     [r14+18h], esi
0x180015913  test    rbx, rbx
0x180015916  jz      short loc_180015927
0x180015918  mov     rax, [rbx]
0x18001591b  mov     rcx, rbx
0x18001591e  mov     rax, [rax+10h]
0x180015922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015927  xor     eax, eax
0x180015929  jmp     loc_18001567C
0x18001592e  test    rdi, rdi
0x180015931  jz      short loc_180015942
0x180015933  mov     rax, [rdi]
0x180015936  mov     rcx, rdi
0x180015939  mov     rax, [rax+10h]
0x18001593d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015942  mov     [rsp+0A8h+var_48], rsi
0x180015947  test    rbx, rbx
0x18001594a  jz      short loc_18001595B
0x18001594c  mov     rax, [rbx]
0x18001594f  mov     rcx, rbx
0x180015952  mov     rax, [rax+10h]
0x180015956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001595b  mov     [rsp+0A8h+var_58], rsi
0x180015960  xor     eax, eax
0x180015962  jmp     loc_180015681
0x180015967  mov     rax, [rcx]
0x18001596a  mov     rax, [rax+10h]
0x18001596e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015973  xor     esi, esi
0x180015975  mov     [rsp+0A8h+var_48], rsi
0x18001597a  mov     rcx, [rsp+0A8h+var_58]
0x18001597f  test    rcx, rcx
0x180015982  jz      short loc_180015990
0x180015984  mov     rax, [rcx]
0x180015987  mov     rax, [rax+10h]
0x18001598b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015990  mov     eax, 80041006h
0x180015995  jmp     loc_18001567C
0x18001599a  mov     eax, 80004004h
0x18001599f  jmp     loc_180015681
0x1800159a4  mov     rdx, [rsp+0A8h+var_50]
0x1800159a9  mov     rcx, r14
0x1800159ac  call    ??4CWbemCallSecurity@@AEAAAEAV0@AEBV0@@Z; CWbemCallSecurity::operator=(CWbemCallSecurity const &)
0x1800159b1  jmp     loc_18001592E
0x1800159b6  mov     rcx, [rsp+0A8h+var_48]
0x1800159bb  test    rcx, rcx
0x1800159be  jnz     short loc_180015967
0x1800159c0  jmp     short loc_180015973
0x1800159c2  mov     rcx, [rsp+0A8h+arg_18]
0x1800159ca  mov     rax, [rcx]
0x1800159cd  mov     rax, [rax+28h]
0x1800159d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159d6  jmp     loc_18001576B
0x1800159db  mov     edx, r14d; int
0x1800159de  lea     rcx, unk_18006A9C0; this
0x1800159e5  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800159ea  jmp     loc_1800157C6
```
