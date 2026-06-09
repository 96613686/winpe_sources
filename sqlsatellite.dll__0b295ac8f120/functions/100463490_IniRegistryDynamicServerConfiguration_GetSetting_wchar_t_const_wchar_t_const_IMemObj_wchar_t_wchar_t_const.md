# IniRegistryDynamicServerConfiguration::GetSetting(wchar_t const *,wchar_t const *,IMemObj *,wchar_t * *,wchar_t const *)

- ea: `0x100463490`
- end: `0x1004637aa`
- name: `?GetSetting@IniRegistryDynamicServerConfiguration@@UEAA_NPEB_W0PEAVIMemObj@@PEAPEA_W0@Z`
- size: `794`
- prototype: `bool(IniRegistryDynamicServerConfiguration *__hidden this, const wchar_t *, const wchar_t *, struct IMemObj *, wchar_t **, const wchar_t *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x100403b90`
- `0x100405270`
- `0x100405390`
- `0x10045c290`
- `0x10045c7c0`
- `0x10045c840`
- `0x100463490`
- `0x100486af0`

## import_xrefs

- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004636d0`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004636d0`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1004634d3`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x1004635a7`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x1004635a7`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1004634f2`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1004634f2`
- `sqldk!??_V@YAXPEAX@Z` at `0x100463747`
- `sqldk!??_V@YAXPEAX@Z` at `0x100463754`
- `sqldk!??_V@YAXPEAX@Z` at `0x100463747`
- `sqldk!??_V@YAXPEAX@Z` at `0x100463754`
- `sqldk!SystemThread_TlsIndex` at `0x100463565`
- `sqldk!SystemThread_TlsIndex` at `0x1004635bc`
- `sqldk!SystemThread_TlsOffset` at `0x10046356e`
- `sqldk!SystemThread_TlsOffset` at `0x1004635c5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100463589`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004635e0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100463589`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004635e0`

## string_xrefs

- `0x1004636c3`: `sql\ntdbms\common\serverconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
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
  signed int v15; // ebx
  unsigned __int64 v16; // rax
  wchar_t *v17; // rdi
  unsigned __int64 v18; // rax
  char v19; // bl
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  DWORD v22[2]; // [rsp+38h] [rbp-C8h] BYREF
  HKEY v23; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *v24; // [rsp+48h] [rbp-B8h]
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
  if ( v8 )
  {
    DefaultLocale = GetDefaultLocale();
    if ( (int)StringCchPrintf_lW(Buffer, 0x105u, L"%ls\\%ls", DefaultLocale, v8, a2) >= 0 )
    {
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
      if ( v28 || (*(_BYTE *)(v14 + 800) & 4) == 0 )
      {
        v27 = 1;
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v14 + 608) + 8LL))(*(_QWORD *)(v14 + 608));
      }
      else
      {
        v27 = 0;
      }
      if ( !(unsigned int)IniRegOpenKeyExW(-2147483646, (int)Buffer, 0, 1, &v23) )
      {
        v22[0] = 0;
        if ( !(unsigned int)IniRegQueryValueExW((int)v23, v6, 0, (int)&v21, 0, v22) && v21 == 1 && (v22[0] & 1) == 0 )
        {
          v15 = (v22[0] >> 1) + 1;
          v16 = 2LL * v15;
          if ( !is_mul_ok(v15, 2u) )
            v16 = -1;
          v17 = (wchar_t *)operator new[](v16, a4, "sql\\ntdbms\\common\\serverconfig.cpp", 144, 6u);
          v24 = v17;
          v17[v15 - 1] = 0;
          if ( !(unsigned int)IniRegQueryValueExW((int)v23, v6, 0, (int)&v21, (LPBYTE)v17, v22)
            && v21 == 1
            && (v22[0] & 1) == 0 )
          {
            if ( v22[0] )
            {
              v18 = (unsigned __int64)v22[0] >> 1;
              if ( v17[v18 - 1] )
                v17[v18] = 0;
            }
            v24 = 0;
            *a5 = v17;
            IniRegCloseKey(v23);
            operator delete[](0);
            v19 = 1;
            goto LABEL_29;
          }
          operator delete[](v17);
        }
        IniRegCloseKey(v23);
      }
      v19 = 0;
LABEL_29:
      AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v27);
      *(_DWORD *)(v26 + 616) &= ~v25;
      return v19;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x100463490  push    rbp
0x100463492  push    rbx
0x100463493  push    rsi
0x100463494  push    rdi
0x100463495  push    r12
0x100463497  push    r14
0x100463499  push    r15
0x10046349b  lea     rbp, [rsp-1E0h]
0x1004634a3  sub     rsp, 2E0h
0x1004634aa  mov     [rbp+210h+var_260], 0FFFFFFFFFFFFFFFEh
0x1004634b2  mov     rax, cs:__security_cookie
0x1004634b9  xor     rax, rsp
0x1004634bc  mov     [rbp+210h+var_40], rax
0x1004634c3  mov     r15, r9
0x1004634c6  mov     rsi, r8
0x1004634c9  mov     rdi, rdx
0x1004634cc  mov     r14, [rbp+210h+arg_20]
0x1004634d3  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x1004634da  mov     rcx, [rax]
0x1004634dd  mov     rax, [rcx]
0x1004634e0  call    qword ptr [rax+110h]
0x1004634e6  mov     rbx, rax
0x1004634e9  test    rax, rax
0x1004634ec  jz      loc_100463787
0x1004634f2  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x1004634f8  mov     r9, rax; struct __crt_locale_pointers *
0x1004634fb  mov     [rsp+310h+var_2E8], rdi
0x100463500  mov     [rsp+310h+var_2F0], rbx
0x100463505  lea     r8, aLsLs_0; "%ls\\%ls"
0x10046350c  mov     edx, 105h; unsigned __int64
0x100463511  lea     rcx, [rbp+210h+Buffer]; Buffer
0x100463515  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x10046351a  test    eax, eax
0x10046351c  js      loc_100463787
0x100463522  mov     edx, 1
0x100463527  lea     rcx, [rsp+310h+var_2C0]
0x10046352c  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x100463531  nop
0x100463532  lea     rax, [rsp+310h+var_2B0]
0x100463537  mov     qword ptr [rsp+310h+var_2D8], rax
0x10046353c  mov     [rsp+310h+var_2A0], 2000026Ah
0x100463544  xor     r12d, r12d
0x100463547  mov     [rsp+310h+var_298], r12
0x10046354c  mov     [rbp+210h+var_288], r12
0x100463550  mov     [rbp+210h+var_290], r12
0x100463554  mov     [rbp+210h+var_280], r12
0x100463558  mov     [rbp+210h+var_270], r12b
0x10046355c  mov     rdx, gs:58h
0x100463565  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10046356c  mov     ecx, [rax]
0x10046356e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100463575  mov     ebx, [rax]
0x100463577  add     rbx, [rdx+rcx*8]
0x10046357b  mov     rax, [rbx+100h]
0x100463582  test    rax, rax
0x100463585  jnz     short loc_100463596
0x100463587  xor     ecx, ecx
0x100463589  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10046358f  mov     rax, [rbx+100h]
0x100463596  mov     rcx, [rax+258h]
0x10046359d  test    rcx, rcx
0x1004635a0  jz      short loc_1004635B3
0x1004635a2  lea     rdx, [rsp+310h+var_2A0]
0x1004635a7  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x1004635ad  test    eax, eax
0x1004635af  setz    [rbp+210h+var_270]
0x1004635b3  mov     rdx, gs:58h
0x1004635bc  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004635c3  mov     ecx, [rax]
0x1004635c5  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004635cc  mov     ebx, [rax]
0x1004635ce  add     rbx, [rdx+rcx*8]
0x1004635d2  mov     rdx, [rbx+100h]
0x1004635d9  test    rdx, rdx
0x1004635dc  jnz     short loc_1004635ED
0x1004635de  xor     ecx, ecx
0x1004635e0  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004635e6  mov     rdx, [rbx+100h]
0x1004635ed  mov     [rsp+310h+var_2A8], rdx
0x1004635f2  mov     eax, [rdx+320h]
0x1004635f8  shr     eax, 0Bh
0x1004635fb  and     eax, 1
0x1004635fe  mov     [rsp+310h+var_2AC], eax
0x100463602  jnz     short loc_100463614
0x100463604  test    byte ptr [rdx+320h], 4
0x10046360b  jz      short loc_100463614
0x10046360d  mov     [rsp+310h+var_2B0], r12d
0x100463612  jmp     short loc_10046362A
0x100463614  mov     [rsp+310h+var_2B0], 1
0x10046361c  mov     rcx, [rdx+260h]
0x100463623  mov     rax, [rcx]
0x100463626  call    qword ptr [rax+8]
0x100463629  nop
0x10046362a  lea     rax, [rsp+310h+var_2D0]
0x10046362f  mov     [rsp+310h+var_2F0], rax; PHKEY
0x100463634  mov     r9d, 1; int
0x10046363a  xor     r8d, r8d; int
0x10046363d  lea     rdx, [rbp+210h+Buffer]; int
0x100463641  mov     rcx, 0FFFFFFFF80000002h; int
0x100463648  call    IniRegOpenKeyExW
0x10046364d  test    eax, eax
0x10046364f  jnz     loc_100463764
0x100463655  mov     [rsp+310h+var_2D8], r12d
0x10046365a  lea     rax, [rsp+310h+var_2D8]
0x10046365f  mov     [rsp+310h+var_2E8], rax; LPDWORD
0x100463664  mov     [rsp+310h+var_2F0], r12; LPBYTE
0x100463669  lea     r9, [rsp+310h+var_2E0]; int
0x10046366e  xor     r8d, r8d; int
0x100463671  mov     rdx, rsi; int
0x100463674  mov     rcx, [rsp+310h+var_2D0]; int
0x100463679  call    IniRegQueryValueExW
0x10046367e  test    eax, eax
0x100463680  jnz     loc_10046375A
0x100463686  cmp     [rsp+310h+var_2E0], 1
0x10046368b  jnz     loc_10046375A
0x100463691  mov     ebx, [rsp+310h+var_2D8]
0x100463695  test    bl, 1
0x100463698  jnz     loc_10046375A
0x10046369e  shr     ebx, 1
0x1004636a0  inc     ebx
0x1004636a2  movsxd  rcx, ebx
0x1004636a5  mov     eax, 2
0x1004636aa  mul     rcx
0x1004636ad  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1004636b4  cmovo   rax, rcx
0x1004636b8  mov     byte ptr [rsp+310h+var_2F0], 6
0x1004636bd  mov     r9d, 90h
0x1004636c3  lea     r8, aSqlNtdbmsCommo; "sql\\ntdbms\\common\\serverconfig.cpp"
0x1004636ca  mov     rdx, r15
0x1004636cd  mov     rcx, rax
0x1004636d0  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004636d6  mov     rdi, rax
0x1004636d9  mov     [rsp+310h+var_2C8], rax
0x1004636de  movsxd  rcx, ebx
0x1004636e1  mov     [rax+rcx*2-2], r12w
0x1004636e7  lea     rax, [rsp+310h+var_2D8]
0x1004636ec  mov     [rsp+310h+var_2E8], rax; LPDWORD
0x1004636f1  mov     [rsp+310h+var_2F0], rdi; LPBYTE
0x1004636f6  lea     r9, [rsp+310h+var_2E0]; int
0x1004636fb  xor     r8d, r8d; int
0x1004636fe  mov     rdx, rsi; int
0x100463701  mov     rcx, [rsp+310h+var_2D0]; int
0x100463706  call    IniRegQueryValueExW
0x10046370b  test    eax, eax
0x10046370d  jnz     short loc_100463751
0x10046370f  cmp     [rsp+310h+var_2E0], 1
0x100463714  jnz     short loc_100463751
0x100463716  mov     eax, [rsp+310h+var_2D8]
0x10046371a  test    al, 1
0x10046371c  jnz     short loc_100463751
0x10046371e  test    eax, eax
0x100463720  jz      short loc_100463732
0x100463722  shr     rax, 1
0x100463725  cmp     word ptr [rdi+rax*2-2], 0
0x10046372b  jz      short loc_100463732
0x10046372d  mov     [rdi+rax*2], r12w
0x100463732  mov     [rsp+310h+var_2C8], r12
0x100463737  mov     [r14], rdi
0x10046373a  mov     rcx, [rsp+310h+var_2D0]
0x10046373f  call    IniRegCloseKey
0x100463744  nop
0x100463745  xor     ecx, ecx
0x100463747  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10046374d  mov     bl, 1
0x10046374f  jmp     short loc_100463766
0x100463751  mov     rcx, rdi
0x100463754  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10046375a  mov     rcx, [rsp+310h+var_2D0]
0x10046375f  call    IniRegCloseKey
0x100463764  xor     bl, bl
0x100463766  lea     rcx, [rsp+310h+var_2B0]; this
0x10046376b  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x100463770  nop
0x100463771  mov     rdx, [rsp+310h+var_2B8]
0x100463776  mov     ecx, [rsp+310h+var_2C0]
0x10046377a  not     ecx
0x10046377c  and     [rdx+268h], ecx
0x100463782  movzx   eax, bl
0x100463785  jmp     short loc_100463789
0x100463787  xor     al, al
0x100463789  mov     rcx, [rbp+210h+var_40]
0x100463790  xor     rcx, rsp; StackCookie
0x100463793  call    __security_check_cookie
0x100463798  add     rsp, 2E0h
0x10046379f  pop     r15
0x1004637a1  pop     r14
0x1004637a3  pop     r12
0x1004637a5  pop     rdi
0x1004637a6  pop     rsi
0x1004637a7  pop     rbx
0x1004637a8  pop     rbp
0x1004637a9  retn
```
