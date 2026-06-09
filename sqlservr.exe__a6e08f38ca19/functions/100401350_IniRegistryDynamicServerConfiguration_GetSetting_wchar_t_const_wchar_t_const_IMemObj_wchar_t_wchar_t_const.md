# IniRegistryDynamicServerConfiguration::GetSetting(wchar_t const *,wchar_t const *,IMemObj *,wchar_t * *,wchar_t const *)

- ea: `0x100401350`
- end: `0x100401577`
- name: `?GetSetting@IniRegistryDynamicServerConfiguration@@UEAA_NPEB_W0PEAVIMemObj@@PEAPEA_W0@Z`
- size: `551`
- prototype: `bool(IniRegistryDynamicServerConfiguration *__hidden this, const wchar_t *, const wchar_t *, struct IMemObj *, wchar_t **, const wchar_t *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x1004012e0`
- `0x100401350`
- `0x100401580`
- `0x100401800`
- `0x1004019a0`
- `0x100401aa0`
- `0x100402080`
- `0x1004021d0`

## import_xrefs

- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100401393`
- `sqldk!??_V@YAXPEAX@Z` at `0x10044d1b3`
- `sqldk!??_V@YAXPEAX@Z` at `0x10044d1c3`
- `sqldk!??_V@YAXPEAX@Z` at `0x10044d1b3`
- `sqldk!??_V@YAXPEAX@Z` at `0x10044d1c3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044d0bf`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044d0d4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044d0bf`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044d0d4`
- `sqldk!SystemThread_TlsOffset` at `0x10040142e`
- `sqldk!SystemThread_TlsOffset` at `0x10040147a`
- `sqldk!SystemThread_TlsIndex` at `0x100401425`
- `sqldk!SystemThread_TlsIndex` at `0x100401471`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1004013b2`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1004013b2`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10044d13c`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10044d13c`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10040145c`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10040145c`

## string_xrefs

- `0x10044d12f`: `sql\ntdbms\common\serverconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
char __fastcall IniRegistryDynamicServerConfiguration::GetSetting(
        IniRegistryDynamicServerConfiguration *this,
        const wchar_t *a2,
        const wchar_t *a3,
        struct IMemObj *a4,
        wchar_t **a5)
{
  int v6; // esi
  __int64 v8; // rbx
  struct __crt_locale_pointers *DefaultLocale; // rax
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rbx
  __int64 v14; // rdx
  char v15; // bl
  signed int v17; // ebx
  unsigned __int64 v18; // rax
  wchar_t *v19; // rdi
  unsigned __int64 v20; // rax
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  DWORD v22[2]; // [rsp+38h] [rbp-C8h] BYREF
  HKEY v23; // [rsp+40h] [rbp-C0h] BYREF
  int *v24; // [rsp+48h] [rbp-B8h]
  int v25; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h] BYREF
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  int v30; // [rsp+70h] [rbp-90h] BYREF
  __int64 v31; // [rsp+78h] [rbp-88h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int64 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+90h] [rbp-70h]
  bool v35; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  wchar_t Buffer[264]; // [rsp+C0h] [rbp-40h] BYREF

  v36 = -2;
  v6 = (int)a3;
  v8 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 272LL))(s_pServerConf);
  if ( !v8 )
    return 0;
  DefaultLocale = GetDefaultLocale();
  if ( (int)StringCchPrintf_lW(Buffer, 0x105u, L"%ls\\%ls", DefaultLocale, v8, a2) < 0 )
    return 0;
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v25, 1);
  *(_QWORD *)v22 = &v27;
  v30 = 536871530;
  v31 = 0;
  v33 = 0;
  v32 = 0;
  v34 = 0;
  v35 = 0;
  v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v11 = *(_QWORD *)(v10 + 256);
  if ( !v11 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v11 = *(_QWORD *)(v10 + 256);
  }
  v12 = *(_QWORD *)(v11 + 600);
  if ( v12 )
    v35 = (unsigned int)SOS_Task::PushWait(v12, &v30) == 0;
  v13 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v14 = *(_QWORD *)(v13 + 256);
  if ( !v14 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v14 = *(_QWORD *)(v13 + 256);
  }
  v29 = v14;
  v28 = (*(_DWORD *)(v14 + 800) >> 11) & 1;
  if ( !v28 && (*(_BYTE *)(v14 + 800) & 4) != 0 )
  {
    v27 = 0;
  }
  else
  {
    v27 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v14 + 608) + 8LL))(*(_QWORD *)(v14 + 608));
  }
  if ( !(unsigned int)IniRegOpenKeyExW(-2147483646, (int)Buffer, 0, 1, &v23) )
  {
    v22[0] = 0;
    if ( !(unsigned int)IniRegQueryValueExW((int)v23, v6, 0, (int)&v21, 0, v22) && v21 == 1 && (v22[0] & 1) == 0 )
    {
      v17 = (v22[0] >> 1) + 1;
      v18 = 2LL * v17;
      if ( !is_mul_ok(v17, 2u) )
        v18 = -1;
      v19 = (wchar_t *)operator new[](v18, a4, "sql\\ntdbms\\common\\serverconfig.cpp", 144, 6u);
      v24 = (int *)v19;
      v19[v17 - 1] = 0;
      if ( !(unsigned int)IniRegQueryValueExW((int)v23, v6, 0, (int)&v21, (LPBYTE)v19, v22)
        && v21 == 1
        && (v22[0] & 1) == 0 )
      {
        if ( v22[0] )
        {
          v20 = (unsigned __int64)v22[0] >> 1;
          if ( v19[v20 - 1] )
            v19[v20] = 0;
        }
        v24 = 0;
        *a5 = v19;
        IniRegCloseKey(v23);
        operator delete[](0);
        v15 = 1;
        goto LABEL_14;
      }
      operator delete[](v19);
    }
    IniRegCloseKey(v23);
  }
  v15 = 0;
LABEL_14:
  v24 = &v27;
  if ( v27 )
  {
    if ( v28 )
      *(_DWORD *)(v29 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v29 + 608) + 16LL))(
        *(_QWORD *)(v29 + 608),
        v29,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v30);
  *(_DWORD *)(v26 + 616) &= ~v25;
  return v15;
}

```

## disassembly

```asm
0x100401350  push    rbp
0x100401352  push    rbx
0x100401353  push    rsi
0x100401354  push    rdi
0x100401355  push    r12
0x100401357  push    r14
0x100401359  push    r15
0x10040135b  lea     rbp, [rsp-1E0h]
0x100401363  sub     rsp, 2E0h
0x10040136a  mov     [rbp+210h+var_260], 0FFFFFFFFFFFFFFFEh
0x100401372  mov     rax, cs:__security_cookie
0x100401379  xor     rax, rsp
0x10040137c  mov     [rbp+210h+var_40], rax
0x100401383  mov     r15, r9
0x100401386  mov     rsi, r8
0x100401389  mov     rdi, rdx
0x10040138c  mov     r14, [rbp+210h+arg_20]
0x100401393  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x10040139a  mov     rcx, [rax]
0x10040139d  mov     rax, [rcx]
0x1004013a0  call    qword ptr [rax+110h]
0x1004013a6  mov     rbx, rax
0x1004013a9  test    rax, rax
0x1004013ac  jz      loc_10044D1E0
0x1004013b2  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x1004013b8  mov     r9, rax; struct __crt_locale_pointers *
0x1004013bb  mov     [rsp+310h+var_2E8], rdi
0x1004013c0  mov     [rsp+310h+var_2F0], rbx
0x1004013c5  lea     r8, aLsLs_1; "%ls\\%ls"
0x1004013cc  mov     edx, 105h; unsigned __int64
0x1004013d1  lea     rcx, [rbp+210h+Buffer]; Buffer
0x1004013d5  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x1004013da  test    eax, eax
0x1004013dc  js      loc_10044D1E0
0x1004013e2  mov     edx, 1
0x1004013e7  lea     rcx, [rsp+310h+var_2C0]
0x1004013ec  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x1004013f1  nop
0x1004013f2  lea     rax, [rsp+310h+var_2B0]
0x1004013f7  mov     qword ptr [rsp+310h+var_2D8], rax
0x1004013fc  mov     [rsp+310h+var_2A0], 2000026Ah
0x100401404  xor     r12d, r12d
0x100401407  mov     [rsp+310h+var_298], r12
0x10040140c  mov     [rbp+210h+var_288], r12
0x100401410  mov     [rbp+210h+var_290], r12
0x100401414  mov     [rbp+210h+var_280], r12
0x100401418  mov     [rbp+210h+var_270], r12b
0x10040141c  mov     rdx, gs:58h
0x100401425  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040142c  mov     ecx, [rax]
0x10040142e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100401435  mov     ebx, [rax]
0x100401437  add     rbx, [rdx+rcx*8]
0x10040143b  mov     rax, [rbx+100h]
0x100401442  test    rax, rax
0x100401445  jz      loc_10044D0BD
0x10040144b  mov     rcx, [rax+258h]
0x100401452  test    rcx, rcx
0x100401455  jz      short loc_100401468
0x100401457  lea     rdx, [rsp+310h+var_2A0]
0x10040145c  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x100401462  test    eax, eax
0x100401464  setz    [rbp+210h+var_270]
0x100401468  mov     rdx, gs:58h
0x100401471  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100401478  mov     ecx, [rax]
0x10040147a  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100401481  mov     ebx, [rax]
0x100401483  add     rbx, [rdx+rcx*8]
0x100401487  mov     rdx, [rbx+100h]
0x10040148e  test    rdx, rdx
0x100401491  jz      loc_10044D0D2
0x100401497  mov     [rsp+310h+var_2A8], rdx
0x10040149c  mov     eax, [rdx+320h]
0x1004014a2  shr     eax, 0Bh
0x1004014a5  and     eax, 1
0x1004014a8  mov     [rsp+310h+var_2AC], eax
0x1004014ac  jnz     short loc_1004014BB
0x1004014ae  test    byte ptr [rdx+320h], 4
0x1004014b5  jnz     loc_10044D0E7
0x1004014bb  mov     [rsp+310h+var_2B0], 1
0x1004014c3  mov     rcx, [rdx+260h]
0x1004014ca  mov     rax, [rcx]
0x1004014cd  call    qword ptr [rax+8]
0x1004014d0  nop
0x1004014d1  lea     rax, [rsp+310h+var_2D0]
0x1004014d6  mov     [rsp+310h+var_2F0], rax; PHKEY
0x1004014db  mov     r9d, 1; int
0x1004014e1  xor     r8d, r8d; int
0x1004014e4  lea     rdx, [rbp+210h+Buffer]; int
0x1004014e8  mov     rcx, 0FFFFFFFF80000002h; int
0x1004014ef  call    IniRegOpenKeyExW
0x1004014f4  test    eax, eax
0x1004014f6  jz      loc_100402274
0x1004014fc  xor     bl, bl
0x1004014fe  lea     rax, [rsp+310h+var_2B0]
0x100401503  mov     [rsp+310h+var_2C8], rax
0x100401508  cmp     [rsp+310h+var_2B0], 0
0x10040150d  jz      short loc_100401534
0x10040150f  mov     rdx, [rsp+310h+var_2A8]
0x100401514  mov     rcx, [rdx+260h]
0x10040151b  cmp     [rsp+310h+var_2AC], 0
0x100401520  jnz     loc_10044D1D0
0x100401526  mov     r9, [rcx]
0x100401529  mov     r8d, 1
0x10040152f  call    qword ptr [r9+10h]
0x100401533  nop
0x100401534  lea     rcx, [rsp+310h+var_2A0]; this
0x100401539  call    ??1SOS_ExternalAutoWait@@QEAA@XZ; SOS_ExternalAutoWait::~SOS_ExternalAutoWait(void)
0x10040153e  nop
0x10040153f  mov     rdx, [rsp+310h+var_2B8]
0x100401544  mov     ecx, [rsp+310h+var_2C0]
0x100401548  not     ecx
0x10040154a  and     [rdx+268h], ecx
0x100401550  movzx   eax, bl
0x100401553  jmp     short loc_100401556
0x100401556  mov     rcx, [rbp+210h+var_40]
0x10040155d  xor     rcx, rsp; StackCookie
0x100401560  call    __security_check_cookie
0x100401565  add     rsp, 2E0h
0x10040156c  pop     r15
0x10040156e  pop     r14
0x100401570  pop     r12
0x100401572  pop     rdi
0x100401573  pop     rsi
0x100401574  pop     rbx
0x100401575  pop     rbp
0x100401576  retn
0x100402274  mov     [rsp+310h+var_2D8], r12d
0x100402279  lea     rax, [rsp+310h+var_2D8]
0x10040227e  mov     [rsp+310h+var_2E8], rax; LPDWORD
0x100402283  mov     [rsp+310h+var_2F0], r12; LPBYTE
0x100402288  lea     r9, [rsp+310h+var_2E0]; int
0x10040228d  xor     r8d, r8d; int
0x100402290  mov     rdx, rsi; int
0x100402293  mov     rcx, [rsp+310h+var_2D0]; int
0x100402298  call    IniRegQueryValueExW
0x10040229d  test    eax, eax
0x10040229f  jz      loc_10044D0F2
0x1004022a5  mov     rcx, [rsp+310h+var_2D0]
0x1004022aa  call    IniRegCloseKey
0x1004022af  nop
0x1004022b0  jmp     loc_1004014FC
0x10044d0bd  xor     ecx, ecx
0x10044d0bf  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044d0c5  mov     rax, [rbx+100h]
0x10044d0cc  jmp     loc_10040144B
0x10044d0d2  xor     ecx, ecx
0x10044d0d4  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044d0da  mov     rdx, [rbx+100h]
0x10044d0e1  jmp     loc_100401497
0x10044d0e7  mov     [rsp+310h+var_2B0], r12d
0x10044d0ec  jmp     loc_1004014D1
0x10044d0f2  cmp     [rsp+310h+var_2E0], 1
0x10044d0f7  jnz     loc_1004022A5
0x10044d0fd  mov     ebx, [rsp+310h+var_2D8]
0x10044d101  test    bl, 1
0x10044d104  jnz     loc_1004022A5
0x10044d10a  shr     ebx, 1
0x10044d10c  inc     ebx
0x10044d10e  movsxd  rcx, ebx
0x10044d111  mov     eax, 2
0x10044d116  mul     rcx
0x10044d119  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10044d120  cmovo   rax, rcx
0x10044d124  mov     byte ptr [rsp+310h+var_2F0], 6
0x10044d129  mov     r9d, 90h
0x10044d12f  lea     r8, aSqlNtdbmsCommo; "sql\\ntdbms\\common\\serverconfig.cpp"
0x10044d136  mov     rdx, r15
0x10044d139  mov     rcx, rax
0x10044d13c  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10044d142  mov     rdi, rax
0x10044d145  mov     [rsp+310h+var_2C8], rax
0x10044d14a  movsxd  rcx, ebx
0x10044d14d  mov     [rax+rcx*2-2], r12w
0x10044d153  lea     rax, [rsp+310h+var_2D8]
0x10044d158  mov     [rsp+310h+var_2E8], rax; LPDWORD
0x10044d15d  mov     [rsp+310h+var_2F0], rdi; LPBYTE
0x10044d162  lea     r9, [rsp+310h+var_2E0]; int
0x10044d167  xor     r8d, r8d; int
0x10044d16a  mov     rdx, rsi; int
0x10044d16d  mov     rcx, [rsp+310h+var_2D0]; int
0x10044d172  call    IniRegQueryValueExW
0x10044d177  test    eax, eax
0x10044d179  jnz     short loc_10044D1C0
0x10044d17b  cmp     [rsp+310h+var_2E0], 1
0x10044d180  jnz     short loc_10044D1C0
0x10044d182  mov     eax, [rsp+310h+var_2D8]
0x10044d186  test    al, 1
0x10044d188  jnz     short loc_10044D1C0
0x10044d18a  test    eax, eax
0x10044d18c  jz      short loc_10044D19E
0x10044d18e  shr     rax, 1
0x10044d191  cmp     word ptr [rdi+rax*2-2], 0
0x10044d197  jz      short loc_10044D19E
0x10044d199  mov     [rdi+rax*2], r12w
0x10044d19e  mov     [rsp+310h+var_2C8], r12
0x10044d1a3  mov     [r14], rdi
0x10044d1a6  mov     rcx, [rsp+310h+var_2D0]
0x10044d1ab  call    IniRegCloseKey
0x10044d1b0  nop
0x10044d1b1  xor     ecx, ecx
0x10044d1b3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10044d1b9  mov     bl, 1
0x10044d1bb  jmp     loc_1004014FE
0x10044d1c0  mov     rcx, rdi
0x10044d1c3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10044d1c9  nop
0x10044d1ca  jmp     loc_1004022A5
0x10044d1d0  or      dword ptr [rdx+320h], 800h
0x10044d1da  jmp     loc_100401534
0x10044d1e0  xor     al, al
0x10044d1e2  jmp     loc_100401556
```
