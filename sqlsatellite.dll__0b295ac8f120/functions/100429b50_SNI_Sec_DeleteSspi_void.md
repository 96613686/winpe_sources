# SNI_Sec::DeleteSspi(void)

- ea: `0x100429b50`
- end: `0x100429dce`
- name: `?DeleteSspi@SNI_Sec@@QEAAXXZ`
- size: `638`
- prototype: `void __fastcall(SNI_Sec *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x100423130`
- `0x100448d90`

## callees

- `0x100405270`
- `0x100405390`
- `0x100429b50`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`

## import_xrefs

- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100429c8a`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100429c8a`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100429d73`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100429d73`
- `sqldk!SystemThread_TlsIndex` at `0x100429c4a`
- `sqldk!SystemThread_TlsIndex` at `0x100429ca0`
- `sqldk!SystemThread_TlsOffset` at `0x100429c53`
- `sqldk!SystemThread_TlsOffset` at `0x100429ca9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100429c6c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100429cc4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100429c6c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100429cc4`

## string_xrefs

- `0x100429b71`: `sql\common\dk\sni\src\sni_sspi.cpp`
- `0x100429b7c`: `SNI_Sec::DeleteSspi`
- `0x100429bc4`: `ERR|SNIUnexpected call to DeleteSspi with IDCRL package outside of SNI_BASED_CLIENT build.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall SNI_Sec::DeleteSspi(SNI_Sec *this, __int64 a2, __int64 a3, const wchar_t *a4)
{
  char v5; // al
  __int64 v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rdi
  __int64 v10; // rdx
  _QWORD *v11; // rcx
  int v12; // [rsp+20h] [rbp-98h] BYREF
  __int64 v13; // [rsp+28h] [rbp-90h]
  int v14; // [rsp+30h] [rbp-88h] BYREF
  int v15; // [rsp+34h] [rbp-84h]
  __int64 v16; // [rsp+38h] [rbp-80h]
  int v17; // [rsp+40h] [rbp-78h] BYREF
  __int64 v18; // [rsp+48h] [rbp-70h]
  __int64 v19; // [rsp+50h] [rbp-68h]
  __int64 v20; // [rsp+58h] [rbp-60h]
  __int64 v21; // [rsp+60h] [rbp-58h]
  bool v22; // [rsp+70h] [rbp-48h]
  __int64 v23; // [rsp+80h] [rbp-38h]
  const char *v24; // [rsp+88h] [rbp-30h]
  const char *v25; // [rsp+90h] [rbp-28h]
  int v26; // [rsp+98h] [rbp-20h]

  v23 = -2;
  v24 = "sql\\common\\dk\\sni\\src\\sni_sspi.cpp";
  v25 = "SNI_Sec::DeleteSspi";
  v26 = 96;
  v5 = g_XeSniPkg_enabledBitmap;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
  {
    SNIXE_SNI_ENTER_ON("sql\\common\\dk\\sni\\src\\sni_sspi.cpp", "SNI_Sec::DeleteSspi", 96, L"API|SNI\n");
    v5 = g_XeSniPkg_enabledBitmap;
  }
  if ( *((_DWORD *)this + 5) == 5 )
  {
    if ( (v5 & 2) != 0 )
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\sni_sspi.cpp",
        "SNI_Sec::DeleteSspi",
        111,
        L"ERR|SNIUnexpected call to DeleteSspi with IDCRL package outside of SNI_BASED_CLIENT build.\n");
  }
  else if ( *((_DWORD *)this + 4) || *((_QWORD *)this + 3) != -1 && *((_QWORD *)this + 4) != -1 || *((_QWORD *)this + 5) )
  {
    Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v12, 1);
    v17 = 536871400;
    v18 = 0;
    v20 = 0;
    v19 = 0;
    v21 = 0;
    v22 = 0;
    v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v7 = *(_QWORD *)(v6 + 256);
    if ( !v7 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v7 = *(_QWORD *)(v6 + 256);
    }
    v8 = *(_QWORD *)(v7 + 600);
    if ( v8 )
      v22 = (unsigned int)SOS_Task::PushWait(v8, &v17) == 0;
    v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v10 = *(_QWORD *)(v9 + 256);
    if ( !v10 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v10 = *(_QWORD *)(v9 + 256);
    }
    v16 = v10;
    v15 = (*(_DWORD *)(v10 + 800) >> 11) & 1;
    if ( v15 || (*(_BYTE *)(v10 + 800) & 4) == 0 )
    {
      v14 = 1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v10 + 608) + 8LL))(*(_QWORD *)(v10 + 608));
    }
    else
    {
      v14 = 0;
    }
    if ( *((_DWORD *)this + 4) )
    {
      ((void (__fastcall *)(SNI_Sec *))g_pFuncs->DeleteSecurityContext)(this);
      *((_DWORD *)this + 4) = 0;
    }
    if ( *((_QWORD *)this + 3) != -1 && *((_QWORD *)this + 4) != -1 )
    {
      ((void (__fastcall *)(char *))g_pFuncs->FreeCredentialsHandle)((char *)this + 24);
      *((_QWORD *)this + 4) = -1;
      *((_QWORD *)this + 3) = -1;
    }
    v11 = (_QWORD *)*((_QWORD *)this + 5);
    if ( v11 )
    {
      ((void (__fastcall *)(_QWORD))g_pFuncs->FreeContextBuffer)(*v11);
      operator delete(*((void **)this + 5), 0x10u);
      *((_QWORD *)this + 5) = 0;
    }
    AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v14);
    a4 = (const wchar_t *)(unsigned int)~v12;
    *(_DWORD *)(v13 + 616) &= (unsigned int)a4;
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni_sspi.cpp", "SNI_Sec::DeleteSspi", 96, a4);
}

```

## disassembly

```asm
0x100429b50  mov     rax, rsp
0x100429b53  push    rsi
0x100429b54  push    rdi
0x100429b55  push    r14
0x100429b57  sub     rsp, 0A0h
0x100429b5e  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x100429b66  mov     [rax+10h], rbx
0x100429b6a  mov     [rax+18h], rbp
0x100429b6e  mov     rbx, rcx
0x100429b71  lea     rsi, aSqlCommonDkSni_20; "sql\\common\\dk\\sni\\src\\sni_sspi.cpp"
0x100429b78  mov     [rax-30h], rsi
0x100429b7c  lea     rbp, aSniSecDeletess; "SNI_Sec::DeleteSspi"
0x100429b83  mov     [rax-28h], rbp
0x100429b87  mov     dword ptr [rax-20h], 60h ; '`'
0x100429b8e  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100429b94  test    al, 40h
0x100429b96  jz      short loc_100429BB6
0x100429b98  lea     r9, aApiSni_0; "API|SNI\n"
0x100429b9f  mov     r8d, 60h ; '`'; int
0x100429ba5  mov     rdx, rbp; char *
0x100429ba8  mov     rcx, rsi; char *
0x100429bab  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100429bb0  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100429bb6  cmp     dword ptr [rbx+14h], 5
0x100429bba  jnz     short loc_100429BE1
0x100429bbc  test    al, 2
0x100429bbe  jz      loc_100429D9C
0x100429bc4  lea     r9, aErrSniunexpect_1; "ERR|SNIUnexpected call to DeleteSspi wi"...
0x100429bcb  mov     r8d, 6Fh ; 'o'; int
0x100429bd1  mov     rdx, rbp; char *
0x100429bd4  mov     rcx, rsi; char *
0x100429bd7  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100429bdc  jmp     loc_100429D9C
0x100429be1  cmp     dword ptr [rbx+10h], 0
0x100429be5  jnz     short loc_100429C00
0x100429be7  cmp     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x100429bec  jz      short loc_100429BF5
0x100429bee  cmp     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x100429bf3  jnz     short loc_100429C00
0x100429bf5  cmp     qword ptr [rbx+28h], 0
0x100429bfa  jz      loc_100429D9C
0x100429c00  mov     edx, 1
0x100429c05  lea     rcx, [rsp+0B8h+var_98]
0x100429c0a  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x100429c0f  nop
0x100429c10  lea     rax, [rsp+0B8h+var_88]
0x100429c15  mov     [rsp+0B8h+arg_0], rax
0x100429c1d  mov     [rsp+0B8h+var_78], 200001E8h
0x100429c25  xor     r14d, r14d
0x100429c28  mov     [rsp+0B8h+var_70], r14
0x100429c2d  mov     [rsp+0B8h+var_60], r14
0x100429c32  mov     [rsp+0B8h+var_68], r14
0x100429c37  mov     [rsp+0B8h+var_58], r14
0x100429c3c  mov     [rsp+0B8h+var_48], r14b
0x100429c41  mov     rdx, gs:58h
0x100429c4a  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100429c51  mov     ecx, [rax]
0x100429c53  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100429c5a  mov     edi, [rax]
0x100429c5c  add     rdi, [rdx+rcx*8]
0x100429c60  mov     rcx, [rdi+100h]
0x100429c67  test    rcx, rcx
0x100429c6a  jnz     short loc_100429C79
0x100429c6c  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100429c72  mov     rcx, [rdi+100h]
0x100429c79  mov     rcx, [rcx+258h]
0x100429c80  test    rcx, rcx
0x100429c83  jz      short loc_100429C97
0x100429c85  lea     rdx, [rsp+0B8h+var_78]
0x100429c8a  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x100429c90  test    eax, eax
0x100429c92  setz    [rsp+0B8h+var_48]
0x100429c97  mov     rdx, gs:58h
0x100429ca0  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100429ca7  mov     ecx, [rax]
0x100429ca9  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100429cb0  mov     edi, [rax]
0x100429cb2  add     rdi, [rdx+rcx*8]
0x100429cb6  mov     rdx, [rdi+100h]
0x100429cbd  test    rdx, rdx
0x100429cc0  jnz     short loc_100429CD1
0x100429cc2  xor     ecx, ecx
0x100429cc4  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100429cca  mov     rdx, [rdi+100h]
0x100429cd1  mov     [rsp+0B8h+var_80], rdx
0x100429cd6  mov     eax, [rdx+320h]
0x100429cdc  shr     eax, 0Bh
0x100429cdf  and     eax, 1
0x100429ce2  mov     [rsp+0B8h+var_84], eax
0x100429ce6  jnz     short loc_100429CF8
0x100429ce8  test    byte ptr [rdx+320h], 4
0x100429cef  jz      short loc_100429CF8
0x100429cf1  mov     [rsp+0B8h+var_88], r14d
0x100429cf6  jmp     short loc_100429D0E
0x100429cf8  mov     [rsp+0B8h+var_88], 1
0x100429d00  mov     rcx, [rdx+260h]
0x100429d07  mov     rax, [rcx]
0x100429d0a  call    qword ptr [rax+8]
0x100429d0d  nop
0x100429d0e  cmp     dword ptr [rbx+10h], 0
0x100429d12  jz      short loc_100429D25
0x100429d14  mov     rcx, rbx
0x100429d17  mov     rax, cs:?g_pFuncs@@3PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * g_pFuncs
0x100429d1e  call    qword ptr [rax+48h]
0x100429d21  mov     [rbx+10h], r14d
0x100429d25  cmp     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x100429d2a  jz      short loc_100429D51
0x100429d2c  cmp     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x100429d31  jz      short loc_100429D51
0x100429d33  lea     rcx, [rbx+18h]
0x100429d37  mov     rax, cs:?g_pFuncs@@3PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * g_pFuncs
0x100429d3e  call    qword ptr [rax+20h]
0x100429d41  mov     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x100429d49  mov     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x100429d51  mov     rcx, [rbx+28h]
0x100429d55  test    rcx, rcx
0x100429d58  jz      short loc_100429D7D
0x100429d5a  mov     rcx, [rcx]
0x100429d5d  mov     rax, cs:?g_pFuncs@@3PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * g_pFuncs
0x100429d64  call    qword ptr [rax+80h]
0x100429d6a  mov     edx, 10h
0x100429d6f  mov     rcx, [rbx+28h]
0x100429d73  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x100429d79  mov     [rbx+28h], r14
0x100429d7d  lea     rcx, [rsp+0B8h+var_88]; this
0x100429d82  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x100429d87  nop
0x100429d88  mov     r9d, [rsp+0B8h+var_98]
0x100429d8d  not     r9d; wchar_t *
0x100429d90  mov     rax, [rsp+0B8h+var_90]
0x100429d95  and     [rax+268h], r9d
0x100429d9c  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100429da3  jz      short loc_100429DB6
0x100429da5  mov     r8d, 60h ; '`'; int
0x100429dab  mov     rdx, rbp; char *
0x100429dae  mov     rcx, rsi; char *
0x100429db1  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x100429db6  lea     r11, [rsp+0B8h+var_18]
0x100429dbe  mov     rbx, [r11+28h]
0x100429dc2  mov     rbp, [r11+30h]
0x100429dc6  mov     rsp, r11
0x100429dc9  pop     r14
0x100429dcb  pop     rdi
0x100429dcc  pop     rsi
0x100429dcd  retn
```
