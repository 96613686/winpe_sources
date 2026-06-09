# HandleScheduleNameConflict(ushort const *,_TASK_TRIGGER const *,HWND__ *,_GUID *)

- ea: `0x18000becc`
- end: `0x18000c1c9`
- name: `?HandleScheduleNameConflict@@YAHPEBGPEBU_TASK_TRIGGER@@PEAUHWND__@@PEAU_GUID@@@Z`
- size: `765`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const struct _TASK_TRIGGER *, HWND, struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000c9c0`

## callees

- `0x180003950`
- `0x18000af60`
- `0x18000af94`
- `0x18000becc`
- `0x18000e110`
- `0x18002924e`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000c118`
- `ole32!CoTaskMemFree` at `0x18000c118`
- `ole32!CoCreateInstance` at `0x18000bf48`
- `ole32!CoCreateInstance` at `0x18000bf48`
- `ole32!CoUninitialize` at `0x18000c1a0`
- `ole32!CoUninitialize` at `0x18000c1a0`
- `ole32!CoInitialize` at `0x18000bf1c`
- `ole32!CoInitialize` at `0x18000bf1c`

## pseudocode

```c
__int64 __fastcall HandleScheduleNameConflict(
        const unsigned __int16 *a1,
        const struct _TASK_TRIGGER *a2,
        HWND a3,
        struct _GUID *a4)
{
  unsigned int v8; // edi
  int v9; // r14d
  BOOL v10; // edx
  int v11; // ecx
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v15; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-B8h] BYREF
  GUID v19; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v20; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v21; // [rsp+62h] [rbp-9Eh]
  _BYTE v22[30]; // [rsp+72h] [rbp-8Eh] BYREF
  unsigned __int16 v23[260]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v24[260]; // [rsp+298h] [rbp+198h] BYREF
  unsigned __int16 v25[264]; // [rsp+4A0h] [rbp+3A0h] BYREF

  ppv = 0;
  *a4 = GUID_NULL;
  v8 = 0;
  if ( CoInitialize(0) >= 0 )
  {
    if ( CoCreateInstance(&CLSID_SyncMgr, 0, 0x17u, &IID_ISyncScheduleMgr, &ppv) < 0 )
    {
LABEL_28:
      CoUninitialize();
      return v8;
    }
    v16 = 0;
    v19 = GUID_NULL;
    StringCchCopyW(v25, 0x104u, a1);
    CWaitCursor::CWaitCursor((CWaitCursor *)&v15);
    v9 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, _QWORD, GUID *, __int64 *))(*(_QWORD *)ppv + 24LL))(
           ppv,
           v25,
           0,
           &v19,
           &v16);
    CWaitCursor::~CWaitCursor((CWaitCursor *)&v15);
    if ( v9 >= 0 )
      goto LABEL_26;
    if ( v9 != -2147220991
      || (*(int (__fastcall **)(LPVOID, GUID *, _QWORD, __int64 *))(*(_QWORD *)ppv + 40LL))(ppv, &v19, 0, &v16) < 0 )
    {
      goto LABEL_27;
    }
    v15 = 0;
    if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 96LL))(v16, &v15) < 0 )
    {
LABEL_26:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
LABEL_27:
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      goto LABEL_28;
    }
    v20 = 48;
    memset(v22, 0, sizeof(v22));
    v21 = 0;
    if ( (*(int (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v15 + 32LL))(v15, &v20) >= 0 )
    {
      v10 = *(_DWORD *)&v22[14] != a2->TriggerType || HIWORD(v21) != a2->wStartHour || *(_WORD *)v22 != a2->wStartMinute;
      v11 = *(_DWORD *)&v22[2] != a2->MinutesDuration || v10 || *(_WORD *)&v22[18] != a2->Type.Daily.DaysInterval;
      if ( *(_WORD *)&v22[28] != a2->wRandomMinutesInterval || v11 | (*(_DWORD *)&v22[6] != a2->MinutesInterval) )
      {
        memset_0(v23, 0, 0x410u);
        pv = 0;
        StringCchCopyW(v23, 0x104u, a1);
        if ( (*(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v15 + 40LL))(v15, &pv) < 0 )
        {
          v24[0] = 0;
        }
        else
        {
          StringCchCopyW(v24, 0x104u, (const unsigned __int16 *)pv);
          CoTaskMemFree(pv);
        }
        v13 = DialogBoxParam(v12, 6024, a3, SchedConflictDlgProc, v23) - 2147;
        if ( v13 )
        {
          if ( v13 != 1 )
          {
            v8 = 3;
            goto LABEL_25;
          }
          v8 = 2;
        }
        else
        {
          v8 = 1;
        }
        *a4 = v19;
      }
    }
LABEL_25:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    goto LABEL_26;
  }
  return v8;
}

```

## disassembly

```asm
0x18000becc  push    rbp
0x18000bece  push    rbx
0x18000becf  push    rsi
0x18000bed0  push    rdi
0x18000bed1  push    r12
0x18000bed3  push    r14
0x18000bed5  push    r15
0x18000bed7  lea     rbp, [rsp-5C0h]
0x18000bedf  sub     rsp, 6C0h
0x18000bee6  mov     rax, cs:__security_cookie
0x18000beed  xor     rax, rsp
0x18000bef0  mov     [rbp+5F0h+var_40], rax
0x18000bef7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000befe  mov     r12, rcx
0x18000bf01  mov     [rsp+6F0h+var_6A8], 0
0x18000bf0a  xor     ecx, ecx; pvReserved
0x18000bf0c  mov     rsi, r9
0x18000bf0f  movdqu  xmmword ptr [r9], xmm0
0x18000bf14  mov     r15, r8
0x18000bf17  mov     rbx, rdx
0x18000bf1a  xor     edi, edi
0x18000bf1c  call    cs:__imp_CoInitialize
0x18000bf22  test    eax, eax
0x18000bf24  js      loc_18000C1A6
0x18000bf2a  lea     rax, [rsp+6F0h+var_6A8]
0x18000bf2f  xor     edx, edx; pUnkOuter
0x18000bf31  lea     r9, IID_ISyncScheduleMgr; riid
0x18000bf38  mov     [rsp+6F0h+ppv], rax; ppv
0x18000bf3d  lea     r8d, [rdi+17h]; dwClsContext
0x18000bf41  lea     rcx, CLSID_SyncMgr; rclsid
0x18000bf48  call    cs:__imp_CoCreateInstance
0x18000bf4e  test    eax, eax
0x18000bf50  js      loc_18000C1A0
0x18000bf56  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000bf5d  mov     r8, r12; unsigned __int16 *
0x18000bf60  mov     [rsp+6F0h+var_6B8], rdi
0x18000bf65  mov     edx, 104h; unsigned __int64
0x18000bf6a  lea     rcx, [rbp+5F0h+var_250]; unsigned __int16 *
0x18000bf71  movdqu  [rsp+6F0h+var_6A0], xmm0
0x18000bf77  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bf7c  lea     rcx, [rsp+6F0h+var_6C0]; this
0x18000bf81  call    ??0CWaitCursor@@QEAA@XZ; CWaitCursor::CWaitCursor(void)
0x18000bf86  mov     rcx, [rsp+6F0h+var_6A8]
0x18000bf8b  lea     rdx, [rsp+6F0h+var_6B8]
0x18000bf90  mov     [rsp+6F0h+ppv], rdx
0x18000bf95  lea     r9, [rsp+6F0h+var_6A0]
0x18000bf9a  xor     r8d, r8d
0x18000bf9d  lea     rdx, [rbp+5F0h+var_250]
0x18000bfa4  mov     rax, [rcx]
0x18000bfa7  mov     rax, [rax+18h]
0x18000bfab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfb0  lea     rcx, [rsp+6F0h+var_6C0]; this
0x18000bfb5  mov     r14d, eax
0x18000bfb8  call    ??1CWaitCursor@@QEAA@XZ; CWaitCursor::~CWaitCursor(void)
0x18000bfbd  test    r14d, r14d
0x18000bfc0  jns     loc_18000C17E
0x18000bfc6  cmp     r14d, 80040201h
0x18000bfcd  jnz     loc_18000C18F
0x18000bfd3  mov     rcx, [rsp+6F0h+var_6A8]
0x18000bfd8  lea     r9, [rsp+6F0h+var_6B8]
0x18000bfdd  xor     r8d, r8d
0x18000bfe0  lea     rdx, [rsp+6F0h+var_6A0]
0x18000bfe5  mov     rax, [rcx]
0x18000bfe8  mov     rax, [rax+28h]
0x18000bfec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bff1  test    eax, eax
0x18000bff3  js      loc_18000C18F
0x18000bff9  mov     rcx, [rsp+6F0h+var_6B8]
0x18000bffe  lea     rdx, [rsp+6F0h+var_6C0]
0x18000c003  mov     [rsp+6F0h+var_6C0], rdi
0x18000c008  mov     rax, [rcx]
0x18000c00b  mov     rax, [rax+60h]
0x18000c00f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c014  test    eax, eax
0x18000c016  js      loc_18000C17E
0x18000c01c  mov     rcx, [rsp+6F0h+var_6C0]
0x18000c021  lea     eax, [rdi+30h]
0x18000c024  xorps   xmm0, xmm0
0x18000c027  mov     [rsp+6F0h+var_690], ax
0x18000c02c  movups  [rsp+6F0h+var_67E], xmm0
0x18000c031  lea     rdx, [rsp+6F0h+var_690]
0x18000c036  movups  [rsp+6F0h+var_68E], xmm0
0x18000c03b  movups  [rbp+5F0h+var_67E+0Eh], xmm0
0x18000c03f  mov     rax, [rcx]
0x18000c042  mov     rax, [rax+20h]
0x18000c046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c04b  test    eax, eax
0x18000c04d  js      loc_18000C16D
0x18000c053  movzx   eax, word ptr [rbx+10h]
0x18000c057  lea     r14d, [rdi+1]
0x18000c05b  xor     ecx, ecx
0x18000c05d  cmp     word ptr [rsp+6F0h+var_68E+0Eh], ax
0x18000c062  movzx   eax, word ptr [rbx+12h]
0x18000c066  setnz   cl
0x18000c069  xor     edx, edx
0x18000c06b  cmp     word ptr [rsp+6F0h+var_67E], ax
0x18000c070  mov     eax, [rbx+20h]
0x18000c073  setnz   dl
0x18000c076  cmp     dword ptr [rbp+5F0h+var_67E+0Eh], eax
0x18000c079  jz      short loc_18000C080
0x18000c07b  mov     edx, r14d
0x18000c07e  jmp     short loc_18000C082
0x18000c080  or      edx, ecx
0x18000c082  movzx   eax, word ptr [rbx+24h]
0x18000c086  xor     ecx, ecx
0x18000c088  cmp     [rbp+5F0h+var_66C], ax
0x18000c08c  mov     eax, [rbx+14h]
0x18000c08f  setnz   cl
0x18000c092  cmp     dword ptr [rsp+6F0h+var_67E+2], eax
0x18000c096  jz      short loc_18000C09D
0x18000c098  mov     ecx, r14d
0x18000c09b  jmp     short loc_18000C09F
0x18000c09d  or      ecx, edx
0x18000c09f  mov     eax, [rbx+18h]
0x18000c0a2  xor     edx, edx
0x18000c0a4  cmp     dword ptr [rsp+6F0h+var_67E+6], eax
0x18000c0a8  movzx   eax, word ptr [rbx+2Eh]
0x18000c0ac  setnz   dl
0x18000c0af  cmp     [rbp+5F0h+var_662], ax
0x18000c0b3  jnz     short loc_18000C0BD
0x18000c0b5  or      edx, ecx
0x18000c0b7  jz      loc_18000C16D
0x18000c0bd  xor     edx, edx; Val
0x18000c0bf  lea     rcx, [rbp+5F0h+var_660]; void *
0x18000c0c3  mov     r8d, 410h; Size
0x18000c0c9  call    memset_0
0x18000c0ce  mov     ebx, 104h
0x18000c0d3  mov     [rsp+6F0h+pv], rdi
0x18000c0d8  mov     edx, ebx; unsigned __int64
0x18000c0da  lea     rcx, [rbp+5F0h+var_660]; unsigned __int16 *
0x18000c0de  mov     r8, r12; unsigned __int16 *
0x18000c0e1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c0e6  mov     rcx, [rsp+6F0h+var_6C0]
0x18000c0eb  lea     rdx, [rsp+6F0h+pv]
0x18000c0f0  mov     rax, [rcx]
0x18000c0f3  mov     rax, [rax+28h]
0x18000c0f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0fc  test    eax, eax
0x18000c0fe  js      short loc_18000C120
0x18000c100  mov     r8, [rsp+6F0h+pv]; unsigned __int16 *
0x18000c105  lea     rcx, [rbp+5F0h+var_458]; unsigned __int16 *
0x18000c10c  mov     edx, ebx; unsigned __int64
0x18000c10e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c113  mov     rcx, [rsp+6F0h+pv]; pv
0x18000c118  call    cs:__imp_CoTaskMemFree
0x18000c11e  jmp     short loc_18000C129
0x18000c120  xor     eax, eax
0x18000c122  mov     [rbp+5F0h+var_458], ax
0x18000c129  lea     rax, [rbp+5F0h+var_660]
0x18000c12d  mov     r8, r15
0x18000c130  lea     r9, ?SchedConflictDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; SchedConflictDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x18000c137  mov     [rsp+6F0h+ppv], rax
0x18000c13c  mov     edx, 1788h
0x18000c141  call    DialogBoxParam
0x18000c146  sub     rax, 863h
0x18000c14c  jz      short loc_18000C161
0x18000c14e  cmp     rax, r14
0x18000c151  jz      short loc_18000C15A
0x18000c153  mov     edi, 3
0x18000c158  jmp     short loc_18000C16D
0x18000c15a  mov     edi, 2
0x18000c15f  jmp     short loc_18000C164
0x18000c161  mov     edi, r14d
0x18000c164  movups  xmm0, [rsp+6F0h+var_6A0]
0x18000c169  movdqu  xmmword ptr [rsi], xmm0
0x18000c16d  mov     rcx, [rsp+6F0h+var_6C0]
0x18000c172  mov     rax, [rcx]
0x18000c175  mov     rax, [rax+10h]
0x18000c179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c17e  mov     rcx, [rsp+6F0h+var_6B8]
0x18000c183  mov     rax, [rcx]
0x18000c186  mov     rax, [rax+10h]
0x18000c18a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c18f  mov     rcx, [rsp+6F0h+var_6A8]
0x18000c194  mov     rdx, [rcx]
0x18000c197  mov     rax, [rdx+10h]
0x18000c19b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1a0  call    cs:__imp_CoUninitialize
0x18000c1a6  mov     eax, edi
0x18000c1a8  mov     rcx, [rbp+5F0h+var_40]
0x18000c1af  xor     rcx, rsp; StackCookie
0x18000c1b2  call    __security_check_cookie
0x18000c1b7  add     rsp, 6C0h
0x18000c1be  pop     r15
0x18000c1c0  pop     r14
0x18000c1c2  pop     r12
0x18000c1c4  pop     rdi
0x18000c1c5  pop     rsi
0x18000c1c6  pop     rbx
0x18000c1c7  pop     rbp
0x18000c1c8  retn
```
