# MpDlpPreCleanup

- ea: `0x140032780`
- end: `0x140032bd1`
- name: `MpDlpPreCleanup`
- size: `1105`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x140030380`

## callees

- `0x140002450`
- `0x1400051bc`
- `0x1400118d0`
- `0x140030060`
- `0x140032780`
- `0x1400346f0`
- `0x140068bf0`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x140032853`
- `ntoskrnl!PsGetProcessId` at `0x140032853`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140032841`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140032841`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140032907`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140032907`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400328fb`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400328fb`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140032889`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140032889`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140032877`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140032877`
- `FLTMGR!FltReleaseContext` at `0x140032b7b`
- `FLTMGR!FltReleaseContext` at `0x14008c7f1`
- `FLTMGR!FltReleaseContext` at `0x140032b7b`
- `FLTMGR!FltReleaseContext` at `0x14008c7f1`
- `FLTMGR!FltReleasePushLock` at `0x140032ab5`
- `FLTMGR!FltReleasePushLock` at `0x140032ab5`
- `FLTMGR!FltGetFileNameInformation` at `0x140032978`
- `FLTMGR!FltGetFileNameInformation` at `0x140032978`
- `FLTMGR!FltGetStreamHandleContext` at `0x1400327d2`
- `FLTMGR!FltGetStreamHandleContext` at `0x1400327d2`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x140032a00`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x140032a00`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032bc3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14008c807`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032bc3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14008c807`

## pseudocode

```c
void __fastcall MpDlpPreCleanup(struct _FLT_CALLBACK_DATA *a1, __int64 a2, __int64 a3)
{
  _QWORD *v6; // rsi
  int v7; // ecx
  bool v8; // r13
  int v9; // ecx
  char v10; // r12
  struct _KPROCESS *RequestorProcess; // rbx
  LONGLONG TimeQuadPart; // r14
  unsigned __int64 ProcessId; // rdi
  char *v14; // rbx
  __int64 v15; // r8
  _QWORD *i; // rax
  volatile signed __int32 *v17; // rcx
  NTSTATUS v18; // eax
  int v19; // r8d
  unsigned __int64 *v20; // rdx
  char *v21; // rax
  char *v22; // rcx
  char **v23; // rdx
  _QWORD *v24; // rax
  char **v25; // rdx
  int v26; // r8d
  __int64 *v27; // rbx
  __int64 *v28; // rdi
  __int64 **v29; // rax
  PFLT_CONTEXT Context; // [rsp+40h] [rbp-58h] BYREF
  __int64 v32; // [rsp+48h] [rbp-50h] BYREF
  char **v33; // [rsp+50h] [rbp-48h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+58h] [rbp-40h] BYREF

  v6 = 0;
  Context = 0;
  FileNameInformation = 0;
  if ( FltGetStreamHandleContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &Context) >= 0 )
  {
    v7 = *(_DWORD *)(*(_QWORD *)(a3 + 8) + 84LL);
    v8 = (v7 & 0x10) != 0 || (v7 & 1) != 0 || (v7 & 4) != 0 || (v7 & 0x800) != 0;
    v9 = *(_DWORD *)(*(_QWORD *)(a2 + 32) + 80LL);
    v10 = (v9 & 0x1000) != 0 || (v9 & 0x2000) != 0 || (*(_DWORD *)(a3 + 48) & 0x100) != 0;
    if ( (*((_DWORD *)Context + 10) & 0x40) != 0 )
    {
      v33 = (char **)&v32;
      v32 = (__int64)&v32;
      FltAcquirePushLockExclusive((PULONG_PTR)Context + 8);
      v20 = (unsigned __int64 *)Context;
      v21 = (char *)Context + 48;
      v22 = (char *)*((_QWORD *)Context + 6);
      if ( v22 != (char *)Context + 48 )
      {
        v23 = (char **)*((_QWORD *)Context + 7);
        if ( *((char **)v22 + 1) != v21
          || *v23 != v21
          || (*v23 = v22,
              *((_QWORD *)v22 + 1) = v23,
              v24 = (char *)Context + 48,
              *((_QWORD *)Context + 7) = (char *)Context + 48,
              *v24 = v24,
              v25 = v33,
              *(__int64 **)(v32 + 8) != &v32)
          || *v33 != (char *)&v32
          || *(char **)(*(_QWORD *)v22 + 8LL) != v22
          || **((char ***)v22 + 1) != v22 )
        {
LABEL_46:
          __fastfail(3u);
        }
        *v33 = v22;
        v33 = (char **)*((_QWORD *)v22 + 1);
        **((_QWORD **)v22 + 1) = &v32;
        *((_QWORD *)v22 + 1) = v25;
        v20 = (unsigned __int64 *)Context;
      }
      FltReleasePushLock(v20 + 8);
      v27 = (__int64 *)v32;
      while ( v27 != &v32 )
      {
        v28 = v27;
        MpDlpOnFileObjectClose(v27[2], (_DWORD)v27 + 24, v26, 1, v10, *(_DWORD *)(*(_QWORD *)(a3 + 8) + 84LL));
        v27 = (__int64 *)*v27;
        v29 = (__int64 **)v28[1];
        if ( (__int64 *)v27[1] != v28 || *v29 != v28 )
          goto LABEL_46;
        *v29 = v27;
        v27[1] = (__int64)v29;
        MpDeleteDlpProcessEntry(v28);
      }
    }
    else
    {
      RequestorProcess = (struct _KPROCESS *)MpGetRequestorProcess(a1);
      TimeQuadPart = PsGetProcessCreateTimeQuadPart(RequestorProcess);
      ProcessId = (unsigned __int64)PsGetProcessId(RequestorProcess);
      if ( ProcessId )
      {
        v14 = (char *)MpProcessTable;
        KeEnterCriticalRegion();
        ExAcquireResourceSharedLite((PERESOURCE)(v14 + 8), 1u);
        v15 = 16 * ((ProcessId >> 2) & 0x7F);
        for ( i = *(_QWORD **)(v15 + *((_QWORD *)MpProcessTable + 48));
              i != (_QWORD *)(v15 + *((_QWORD *)MpProcessTable + 48));
              i = (_QWORD *)*i )
        {
          v17 = (volatile signed __int32 *)(i - 1);
          if ( ProcessId == i[2] && TimeQuadPart == *((_QWORD *)v17 + 4) )
          {
            _InterlockedIncrement(v17 + 12);
            v6 = i - 1;
            break;
          }
        }
        ExReleaseResourceLite((PERESOURCE)((char *)MpProcessTable + 8));
        KeLeaveCriticalRegion();
      }
      if ( v6
        && (*((_BYTE *)v6 + 232)
         || MpDlpData && *((_BYTE *)MpDlpData + 32) && v10 && v8 && (*((_DWORD *)MpDlpData + 68) & 4) != 0) )
      {
        v18 = FltGetFileNameInformation(a1, 0x102u, &FileNameInformation);
        if ( v18 >= 0 )
        {
          if ( FileNameInformation )
            MpDlpOnFileObjectClose(
              (_DWORD)v6,
              (_DWORD)FileNameInformation + 8,
              v19,
              2,
              v10,
              *(_DWORD *)(*(_QWORD *)(a3 + 8) + 84LL));
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          _mm_lfence();
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            49,
            WPP_b54df57aea2c34b04f95f22ee0a6a450_Traceguids,
            KeGetCurrentThread(),
            v18);
        }
      }
    }
  }
  if ( v6 )
    MpReleaseProcessContext(v6);
  if ( Context )
    FltReleaseContext(Context);
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
}

```

## disassembly

```asm
0x140032780  mov     [rsp+arg_10], rbx
0x140032785  mov     [rsp+arg_18], rsi
0x14003278a  push    rdi
0x14003278b  push    r12
0x14003278d  push    r13
0x14003278f  push    r14
0x140032791  push    r15
0x140032793  sub     rsp, 70h
0x140032797  mov     rax, cs:__security_cookie
0x14003279e  xor     rax, rsp
0x1400327a1  mov     [rsp+98h+var_38], rax
0x1400327a6  mov     r15, r8
0x1400327a9  mov     rbx, rdx
0x1400327ac  mov     rdi, rcx
0x1400327af  mov     [rsp+98h+CallbackData], rcx
0x1400327b4  xor     esi, esi
0x1400327b6  mov     [rsp+98h+Context], rsi
0x1400327bb  mov     [rsp+98h+var_68], rsi
0x1400327c0  mov     [rsp+98h+FileNameInformation], rsi
0x1400327c5  lea     r8, [rsp+98h+Context]; Context
0x1400327ca  mov     rdx, [rdx+20h]; FileObject
0x1400327ce  mov     rcx, [rbx+18h]; Instance
0x1400327d2  call    cs:__imp_FltGetStreamHandleContext
0x1400327d9  nop     dword ptr [rax+rax+00h]
0x1400327de  test    eax, eax
0x1400327e0  js      loc_140032B6C
0x1400327e6  mov     rax, [r15+8]
0x1400327ea  mov     ecx, [rax+54h]
0x1400327ed  test    cl, 10h
0x1400327f0  jnz     short loc_1400327FB
0x1400327f2  test    cl, 1
0x1400327f5  jz      loc_140032B1D
0x1400327fb  mov     r13b, 1
0x1400327fe  mov     rax, [rbx+20h]
0x140032802  mov     ecx, [rax+50h]
0x140032805  bt      ecx, 0Ch
0x140032809  jb      short loc_140032820
0x14003280b  bt      ecx, 0Dh
0x14003280f  jb      short loc_140032820
0x140032811  test    dword ptr [r15+30h], 100h
0x140032819  jnz     short loc_140032820
0x14003281b  xor     r12b, r12b
0x14003281e  jmp     short loc_140032823
0x140032820  mov     r12b, 1
0x140032823  mov     rcx, [rsp+98h+Context]
0x140032828  mov     eax, [rcx+28h]
0x14003282b  test    al, 40h
0x14003282d  jnz     loc_1400329E0
0x140032833  mov     rcx, rdi
0x140032836  call    MpGetRequestorProcess
0x14003283b  mov     rbx, rax
0x14003283e  mov     rcx, rax; Process
0x140032841  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x140032848  nop     dword ptr [rax+rax+00h]
0x14003284d  mov     r14, rax
0x140032850  mov     rcx, rbx; Process
0x140032853  call    cs:__imp_PsGetProcessId
0x14003285a  nop     dword ptr [rax+rax+00h]
0x14003285f  mov     rdi, rax
0x140032862  mov     [rsp+98h+var_68], rsi
0x140032867  test    rax, rax
0x14003286a  jz      loc_140032913
0x140032870  mov     rbx, cs:MpProcessTable
0x140032877  call    cs:__imp_KeEnterCriticalRegion
0x14003287e  nop     dword ptr [rax+rax+00h]
0x140032883  mov     dl, 1; Wait
0x140032885  lea     rcx, [rbx+8]; Resource
0x140032889  call    cs:__imp_ExAcquireResourceSharedLite
0x140032890  nop     dword ptr [rax+rax+00h]
0x140032895  mov     r8, rdi
0x140032898  shr     r8, 2
0x14003289c  and     r8d, 7Fh
0x1400328a0  shl     r8, 4
0x1400328a4  mov     r9, cs:MpProcessTable
0x1400328ab  mov     rax, [r9+180h]
0x1400328b2  mov     rax, [r8+rax]
0x1400328b6  nop     word ptr [rax+rax+00000000h]
0x1400328c0  mov     rdx, [r9+180h]
0x1400328c7  add     rdx, r8
0x1400328ca  cmp     rax, rdx
0x1400328cd  jz      short loc_1400328F0
0x1400328cf  lea     rcx, [rax-8]
0x1400328d3  cmp     rdi, [rcx+18h]
0x1400328d7  jz      short loc_1400328DE
0x1400328d9  mov     rax, [rax]
0x1400328dc  jmp     short loc_1400328C0
0x1400328de  cmp     r14, [rcx+20h]
0x1400328e2  jnz     short loc_1400328D9
0x1400328e4  lock inc dword ptr [rcx+30h]
0x1400328e8  mov     rsi, rcx
0x1400328eb  mov     [rsp+98h+var_68], rcx
0x1400328f0  mov     rcx, cs:MpProcessTable
0x1400328f7  add     rcx, 8; Resource
0x1400328fb  call    cs:__imp_ExReleaseResourceLite
0x140032902  nop     dword ptr [rax+rax+00h]
0x140032907  call    cs:__imp_KeLeaveCriticalRegion
0x14003290e  nop     dword ptr [rax+rax+00h]
0x140032913  test    rsi, rsi
0x140032916  jz      loc_140032B6C
0x14003291c  cmp     byte ptr [rsi+0E8h], 0
0x140032923  jnz     short loc_140032969
0x140032925  mov     rax, cs:MpDlpData
0x14003292c  test    rax, rax
0x14003292f  jz      loc_140032B6C
0x140032935  movzx   eax, byte ptr [rax+20h]
0x140032939  test    al, al
0x14003293b  jz      loc_140032B6C
0x140032941  test    r12b, r12b
0x140032944  jz      loc_140032B6C
0x14003294a  test    r13b, r13b
0x14003294d  jz      loc_140032B6C
0x140032953  mov     rax, cs:MpDlpData
0x14003295a  mov     edx, [rax+110h]
0x140032960  test    dl, 4
0x140032963  jz      loc_140032B6C
0x140032969  lea     r8, [rsp+98h+FileNameInformation]; FileNameInformation
0x14003296e  mov     edx, 102h; NameOptions
0x140032973  mov     rcx, [rsp+98h+CallbackData]; CallbackData
0x140032978  call    cs:__imp_FltGetFileNameInformation
0x14003297f  nop     dword ptr [rax+rax+00h]
0x140032984  test    eax, eax
0x140032986  jns     loc_140032B3F
0x14003298c  lea     rdx, WPP_GLOBAL_Control
0x140032993  mov     rcx, cs:WPP_GLOBAL_Control
0x14003299a  cmp     rcx, rdx
0x14003299d  jz      loc_140032B6C
0x1400329a3  mov     ecx, [rcx+2Ch]
0x1400329a6  test    cl, 1
0x1400329a9  jz      loc_140032B6C
0x1400329af  lfence
0x1400329b2  mov     r9, gs:188h
0x1400329bb  mov     edx, 31h ; '1'
0x1400329c0  mov     [rsp+98h+var_78], eax
0x1400329c4  lea     r8, WPP_b54df57aea2c34b04f95f22ee0a6a450_Traceguids
0x1400329cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400329d2  mov     rcx, [rcx+18h]
0x1400329d6  call    WPP_SF_qD
0x1400329db  jmp     loc_140032B6C
0x1400329e0  xorps   xmm0, xmm0
0x1400329e3  movups  [rsp+98h+var_50], xmm0
0x1400329e8  lea     rax, [rsp+98h+var_50]
0x1400329ed  mov     qword ptr [rsp+98h+var_50+8], rax
0x1400329f2  lea     rax, [rsp+98h+var_50]
0x1400329f7  mov     qword ptr [rsp+98h+var_50], rax
0x1400329fc  add     rcx, 40h ; '@'; PushLock
0x140032a00  call    cs:__imp_FltAcquirePushLockExclusive
0x140032a07  nop     dword ptr [rax+rax+00h]
0x140032a0c  mov     rdx, [rsp+98h+Context]
0x140032a11  lea     rax, [rdx+30h]
0x140032a15  mov     rcx, [rax]
0x140032a18  cmp     rcx, rax
0x140032a1b  jz      loc_140032AB1
0x140032a21  mov     rdx, [rax+8]
0x140032a25  cmp     [rcx+8], rax
0x140032a29  jnz     loc_140032B38
0x140032a2f  cmp     [rdx], rax
0x140032a32  jnz     loc_140032B38
0x140032a38  mov     [rdx], rcx
0x140032a3b  mov     [rcx+8], rdx
0x140032a3f  mov     rax, [rsp+98h+Context]
0x140032a44  add     rax, 30h ; '0'
0x140032a48  mov     [rax+8], rax
0x140032a4c  mov     [rax], rax
0x140032a4f  mov     rdx, qword ptr [rsp+98h+var_50+8]
0x140032a54  lea     r8, [rsp+98h+var_50]
0x140032a59  mov     rax, qword ptr [rsp+98h+var_50]
0x140032a5e  cmp     [rax+8], r8
0x140032a62  jnz     loc_140032B38
0x140032a68  lea     rax, [rsp+98h+var_50]
0x140032a6d  cmp     [rdx], rax
0x140032a70  jnz     loc_140032B38
0x140032a76  mov     rax, [rcx]
0x140032a79  cmp     [rax+8], rcx
0x140032a7d  jnz     loc_140032B38
0x140032a83  mov     rax, [rcx+8]
0x140032a87  cmp     [rax], rcx
0x140032a8a  jnz     loc_140032B38
0x140032a90  mov     [rdx], rcx
0x140032a93  mov     rax, [rcx+8]
0x140032a97  mov     qword ptr [rsp+98h+var_50+8], rax
0x140032a9c  mov     rax, [rcx+8]
0x140032aa0  lea     r8, [rsp+98h+var_50]
0x140032aa5  mov     [rax], r8
0x140032aa8  mov     [rcx+8], rdx
0x140032aac  mov     rdx, [rsp+98h+Context]
0x140032ab1  lea     rcx, [rdx+40h]; PushLock
0x140032ab5  call    cs:__imp_FltReleasePushLock
0x140032abc  nop     dword ptr [rax+rax+00h]
0x140032ac1  mov     rbx, qword ptr [rsp+98h+var_50]
0x140032ac6  lea     rax, [rsp+98h+var_50]
0x140032acb  cmp     rbx, rax
0x140032ace  jz      loc_140032B6C
0x140032ad4  mov     rdi, rbx
0x140032ad7  mov     rax, [r15+8]
0x140032adb  lea     rdx, [rbx+18h]
0x140032adf  mov     eax, [rax+54h]
0x140032ae2  mov     [rsp+98h+var_70], eax
0x140032ae6  mov     byte ptr [rsp+98h+var_78], r12b
0x140032aeb  mov     r9d, 1
0x140032af1  mov     rcx, [rbx+10h]
0x140032af5  call    MpDlpOnFileObjectClose
0x140032afa  mov     rbx, [rbx]
0x140032afd  mov     rax, [rdi+8]
0x140032b01  cmp     [rbx+8], rdi
0x140032b05  jnz     short loc_140032B38
0x140032b07  cmp     [rax], rdi
0x140032b0a  jnz     short loc_140032B38
0x140032b0c  mov     [rax], rbx
0x140032b0f  mov     [rbx+8], rax
0x140032b13  mov     rcx, rdi
0x140032b16  call    MpDeleteDlpProcessEntry
0x140032b1b  jmp     short loc_140032AC6
0x140032b1d  test    cl, 4
0x140032b20  jnz     loc_1400327FB
0x140032b26  bt      ecx, 0Bh
0x140032b2a  jb      loc_1400327FB
0x140032b30  xor     r13b, r13b
0x140032b33  jmp     loc_1400327FE
0x140032b38  mov     ecx, 3
0x140032b3d  int     29h; Win8: RtlFailFast(ecx)
0x140032b3f  mov     rcx, [rsp+98h+FileNameInformation]
0x140032b44  test    rcx, rcx
0x140032b47  jz      short loc_140032B6C
0x140032b49  mov     rax, [r15+8]
0x140032b4d  lea     rdx, [rcx+8]
0x140032b51  mov     eax, [rax+54h]
0x140032b54  mov     [rsp+98h+var_70], eax
0x140032b58  mov     byte ptr [rsp+98h+var_78], r12b
0x140032b5d  mov     r9d, 2
0x140032b63  mov     rcx, rsi
0x140032b66  call    MpDlpOnFileObjectClose
0x140032b6b  nop
0x140032b6c  test    rsi, rsi
0x140032b6f  jnz     short loc_140032BB9
0x140032b71  mov     rcx, [rsp+98h+Context]; Context
0x140032b76  test    rcx, rcx
0x140032b79  jz      short loc_140032B87
0x140032b7b  call    cs:__imp_FltReleaseContext
0x140032b82  nop     dword ptr [rax+rax+00h]
0x140032b87  mov     rcx, [rsp+98h+FileNameInformation]; FileNameInformation
0x140032b8c  test    rcx, rcx
0x140032b8f  jnz     short loc_140032BC3
0x140032b91  mov     rcx, [rsp+98h+var_38]
0x140032b96  xor     rcx, rsp; StackCookie
0x140032b99  call    __security_check_cookie
0x140032b9e  lea     r11, [rsp+98h+var_28]
0x140032ba3  mov     rbx, [r11+40h]
0x140032ba7  mov     rsi, [r11+48h]
0x140032bab  mov     rsp, r11
0x140032bae  pop     r15
0x140032bb0  pop     r14
0x140032bb2  pop     r13
0x140032bb4  pop     r12
0x140032bb6  pop     rdi
0x140032bb7  retn
0x140032bb9  mov     rcx, rsi
0x140032bbc  call    MpReleaseProcessContext
0x140032bc1  jmp     short loc_140032B71
0x140032bc3  call    cs:__imp_FltReleaseFileNameInformation
0x140032bca  nop     dword ptr [rax+rax+00h]
0x140032bcf  jmp     short loc_140032B91
0x14008c7d0  push    rbp
0x14008c7d2  sub     rsp, 30h
0x14008c7d6  mov     rbp, rdx
0x14008c7d9  mov     rcx, [rbp+30h]
0x14008c7dd  test    rcx, rcx
0x14008c7e0  jz      short loc_14008C7E8
0x14008c7e2  call    MpReleaseProcessContext
0x14008c7e7  nop
0x14008c7e8  mov     rcx, [rbp+40h]; Context
0x14008c7ec  test    rcx, rcx
0x14008c7ef  jz      short loc_14008C7FE
0x14008c7f1  call    cs:__imp_FltReleaseContext
0x14008c7f8  nop     dword ptr [rax+rax+00h]
0x14008c7fd  nop
0x14008c7fe  mov     rcx, [rbp+58h]; FileNameInformation
0x14008c802  test    rcx, rcx
0x14008c805  jz      short loc_14008C814
0x14008c807  call    cs:__imp_FltReleaseFileNameInformation
0x14008c80e  nop     dword ptr [rax+rax+00h]
0x14008c813  nop
0x14008c814  add     rsp, 30h
0x14008c818  pop     rbp
0x14008c819  retn
```
