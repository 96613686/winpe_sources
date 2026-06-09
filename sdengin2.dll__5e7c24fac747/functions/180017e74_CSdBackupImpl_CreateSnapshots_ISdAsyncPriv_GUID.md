# CSdBackupImpl::_CreateSnapshots(ISdAsyncPriv *,_GUID *)

- ea: `0x180017e74`
- end: `0x180018162`
- name: `?_CreateSnapshots@CSdBackupImpl@@AEAAJPEAUISdAsyncPriv@@PEAU_GUID@@@Z`
- size: `750`
- prototype: `__int64 __fastcall(CSdBackupImpl *__hidden this, struct ISdAsyncPriv *, struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003dee0`

## callees

- `0x180016f28`
- `0x180017e74`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180070564`
- `0x180099fd8`
- `0x18009ae34`
- `0x1800c9830`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180017f51`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180017f51`
- `ole32!CoTaskMemFree` at `0x1800180e6`
- `ole32!CoTaskMemFree` at `0x1800180ff`
- `ole32!CoTaskMemFree` at `0x1800180e6`
- `ole32!CoTaskMemFree` at `0x1800180ff`

## string_xrefs

- `0x180017eac`: `CSdBackupImpl::_CreateSnapshots`

## pseudocode

```c
__int64 __fastcall CSdBackupImpl::_CreateSnapshots(CSdBackupImpl *this, struct ISdAsyncPriv *a2, struct _GUID *a3)
{
  __int64 v6; // rcx
  struct _GUID *v7; // rax
  __int16 v8; // ax
  int StringResource; // ebx
  __int64 v10; // rcx
  __int64 v11; // rcx
  unsigned int i; // edi
  int v13; // eax
  unsigned int v15; // [rsp+50h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-51h] BYREF
  int v17; // [rsp+60h] [rbp-49h] BYREF
  __int16 v18; // [rsp+64h] [rbp-45h]
  __int16 v19; // [rsp+66h] [rbp-43h]
  int v20; // [rsp+98h] [rbp-11h] BYREF
  _QWORD v21[2]; // [rsp+A0h] [rbp-9h] BYREF
  __int128 v22; // [rsp+B0h] [rbp+7h] BYREF
  GUID v23; // [rsp+C0h] [rbp+17h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v17, "CSdBackupImpl::_CreateSnapshots", 1237, 0);
  v23 = GUID_NULL;
  v20 = 0;
  pv = 0;
  v15 = 0;
  v21[0] = qword_1800E8530;
  v21[1] = 0;
  if ( a3 )
  {
    v6 = 16;
    v7 = a3;
    do
    {
      LOBYTE(v7->Data1) = 0;
      v7 = (struct _GUID *)((char *)v7 + 1);
      --v6;
    }
    while ( v6 );
  }
  v8 = 1253;
  if ( !a2 )
  {
    StringResource = -2147024809;
    v17 = -2147024809;
LABEL_6:
    v19 = v8;
    goto LABEL_15;
  }
  v17 = 0;
  v18 = 1253;
  StringResource = CSxFunctionTracer::_SetContextHelper((CSxFunctionTracer *)&v17, hInstance, 0x4E21u, 0, 0);
  v17 = StringResource;
  v8 = 1255;
  if ( StringResource < 0 )
    goto LABEL_6;
  v18 = 1255;
  RevertToSelf();
  StringResource = CSdBackupImpl::_BuildVolumePathsForSnapshot(this, a2, &v15, (unsigned __int16 ***)&pv);
  v17 = StringResource;
  v8 = 1261;
  if ( StringResource < 0 )
    goto LABEL_6;
  v18 = 1261;
  StringResource = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 44) + 208LL))(
                     *((_QWORD *)this + 44),
                     &v20);
  v17 = StringResource;
  v8 = 1263;
  if ( StringResource < 0 )
    goto LABEL_6;
  v18 = 1263;
  v10 = *((_QWORD *)this + 88);
  v22 = xmmword_1800DBDC8;
  StringResource = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64, _QWORD, LPVOID))(*(_QWORD *)v10 + 88LL))(
                     v10,
                     &v22,
                     1,
                     v15,
                     pv);
  v17 = StringResource;
  v8 = 1276;
  if ( StringResource < 0 )
    goto LABEL_6;
  v18 = 1276;
  v11 = *((_QWORD *)this + 88);
  v22 = xmmword_1800DBDC8;
  StringResource = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)v11 + 248LL))(
                     v11,
                     &v22,
                     86400000);
  v17 = StringResource;
  v8 = 1279;
  if ( StringResource < 0 )
    goto LABEL_6;
  v18 = 1279;
  StringResource = CBsString::LoadStringResource((CBsString *)v21, hInstance, 0xCCu);
  v17 = StringResource;
  v8 = 1282;
  if ( StringResource < 0 )
    goto LABEL_6;
  v18 = 1282;
  StringResource = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, bool, int, _QWORD, _DWORD, GUID *))(**((_QWORD **)this + 88) + 24LL))(
                     *((_QWORD *)this + 88),
                     15,
                     v21[0],
                     (*((_DWORD *)this + 47) & 2) == 0,
                     7,
                     0,
                     0,
                     &v23);
  v17 = StringResource;
  v8 = 1294;
  if ( StringResource < 0 )
    goto LABEL_6;
  v18 = 1294;
  *a3 = v23;
LABEL_15:
  if ( pv )
  {
    for ( i = 0; i < v15; ++i )
    {
      CoTaskMemFree(*((LPVOID *)pv + i));
      *((_QWORD *)pv + i) = 0;
    }
    CoTaskMemFree(pv);
    pv = 0;
    StringResource = v17;
  }
  if ( a2 )
  {
    v13 = (*(__int64 (__fastcall **)(struct ISdAsyncPriv *))(*(_QWORD *)a2 + 96LL))(a2);
    StringResource = v17;
    if ( v17 >= 0 )
      StringResource = v13;
    v17 = StringResource;
  }
  CBsString::_Release((CBsString *)v21);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v17);
  return (unsigned int)StringResource;
}

```

## disassembly

```asm
0x180017e74  mov     [rsp-8+arg_18], rbx
0x180017e79  push    rbp
0x180017e7a  push    rsi
0x180017e7b  push    rdi
0x180017e7c  push    r14
0x180017e7e  push    r15
0x180017e80  lea     rbp, [rsp-37h]
0x180017e85  sub     rsp, 0E0h
0x180017e8c  mov     rax, cs:__security_cookie
0x180017e93  xor     rax, rsp
0x180017e96  mov     [rbp+57h+var_30], rax
0x180017e9a  mov     r14, r8
0x180017e9d  mov     rsi, rdx
0x180017ea0  mov     rdi, rcx
0x180017ea3  xor     r9d, r9d; unsigned __int16
0x180017ea6  mov     r8d, 4D5h; unsigned __int16
0x180017eac  lea     rdx, aCsdbackupimplC_8; "CSdBackupImpl::_CreateSnapshots"
0x180017eb3  lea     rcx, [rbp+57h+var_A0]; this
0x180017eb7  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180017ebc  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180017ec3  movdqu  [rbp+57h+var_40], xmm0
0x180017ec8  xor     r15d, r15d
0x180017ecb  mov     [rbp+57h+var_68], r15d
0x180017ecf  mov     [rbp+57h+pv], r15
0x180017ed3  mov     [rbp+57h+var_B0], r15d
0x180017ed7  lea     rax, qword_1800E8530
0x180017ede  mov     [rbp+57h+var_60], rax
0x180017ee2  mov     [rbp+57h+var_58], r15
0x180017ee6  test    r14, r14
0x180017ee9  jz      short loc_180017EFE
0x180017eeb  lea     ecx, [r15+10h]
0x180017eef  mov     rax, r14
0x180017ef2  mov     [rax], r15b
0x180017ef5  inc     rax
0x180017ef8  sub     rcx, 1
0x180017efc  jnz     short loc_180017EF2
0x180017efe  mov     eax, 4E5h
0x180017f03  test    rsi, rsi
0x180017f06  jnz     short loc_180017F19
0x180017f08  mov     ebx, 80070057h
0x180017f0d  mov     [rbp+57h+var_A0], ebx
0x180017f10  mov     [rbp+57h+var_9A], ax
0x180017f14  jmp     loc_1800180CD
0x180017f19  mov     [rbp+57h+var_A0], r15d
0x180017f1d  mov     [rbp+57h+var_9C], ax
0x180017f21  mov     [rsp+100h+var_E0], r15; unsigned __int16 **
0x180017f26  xor     r9d, r9d; unsigned int
0x180017f29  mov     r8d, 4E21h; unsigned int
0x180017f2f  mov     rdx, cs:hInstance; HINSTANCE
0x180017f36  lea     rcx, [rbp+57h+var_A0]; this
0x180017f3a  call    ?_SetContextHelper@CSxFunctionTracer@@AEAAJPEAUHINSTANCE__@@KKPEAPEBG@Z; CSxFunctionTracer::_SetContextHelper(HINSTANCE__ *,ulong,ulong,ushort const * *)
0x180017f3f  mov     ebx, eax
0x180017f41  mov     [rbp+57h+var_A0], eax
0x180017f44  test    eax, eax
0x180017f46  mov     eax, 4E7h
0x180017f4b  js      short loc_180017F10
0x180017f4d  mov     [rbp+57h+var_9C], ax
0x180017f51  call    cs:__imp_RevertToSelf
0x180017f57  lea     r9, [rbp+57h+pv]; unsigned __int16 ***
0x180017f5b  lea     r8, [rbp+57h+var_B0]; unsigned int *
0x180017f5f  mov     rdx, rsi; struct ISdAsyncPriv *
0x180017f62  mov     rcx, rdi; this
0x180017f65  call    ?_BuildVolumePathsForSnapshot@CSdBackupImpl@@AEAAJPEAUISdAsyncPriv@@PEAKPEAPEAPEAG@Z; CSdBackupImpl::_BuildVolumePathsForSnapshot(ISdAsyncPriv *,ulong *,ushort * * *)
0x180017f6a  mov     ebx, eax
0x180017f6c  mov     [rbp+57h+var_A0], eax
0x180017f6f  test    eax, eax
0x180017f71  mov     eax, 4EDh
0x180017f76  js      short loc_180017F10
0x180017f78  mov     [rbp+57h+var_9C], ax
0x180017f7c  mov     rcx, [rdi+160h]
0x180017f83  mov     rax, [rcx]
0x180017f86  lea     rdx, [rbp+57h+var_68]
0x180017f8a  mov     rax, [rax+0D0h]
0x180017f91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f96  mov     ebx, eax
0x180017f98  mov     [rbp+57h+var_A0], eax
0x180017f9b  test    eax, eax
0x180017f9d  mov     eax, 4EFh
0x180017fa2  js      loc_180017F10
0x180017fa8  mov     [rbp+57h+var_9C], ax
0x180017fac  mov     rcx, [rdi+2C0h]
0x180017fb3  movups  xmm0, cs:xmmword_1800DBDC8
0x180017fba  movdqu  [rbp+57h+var_50], xmm0
0x180017fbf  mov     rax, [rcx]
0x180017fc2  mov     rdx, [rbp+57h+pv]
0x180017fc6  mov     [rsp+100h+var_E0], rdx
0x180017fcb  mov     r9d, [rbp+57h+var_B0]
0x180017fcf  mov     r8d, 1
0x180017fd5  lea     rdx, [rbp+57h+var_50]
0x180017fd9  mov     rax, [rax+58h]
0x180017fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fe2  mov     ebx, eax
0x180017fe4  mov     [rbp+57h+var_A0], eax
0x180017fe7  test    eax, eax
0x180017fe9  mov     eax, 4FCh
0x180017fee  js      loc_180017F10
0x180017ff4  mov     [rbp+57h+var_9C], ax
0x180017ff8  mov     rcx, [rdi+2C0h]
0x180017fff  movups  xmm0, cs:xmmword_1800DBDC8
0x180018006  movdqu  [rbp+57h+var_50], xmm0
0x18001800b  mov     rax, [rcx]
0x18001800e  mov     r8d, 5265C00h
0x180018014  lea     rdx, [rbp+57h+var_50]
0x180018018  mov     rax, [rax+0F8h]
0x18001801f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018024  mov     ebx, eax
0x180018026  mov     [rbp+57h+var_A0], eax
0x180018029  test    eax, eax
0x18001802b  mov     eax, 4FFh
0x180018030  js      loc_180017F10
0x180018036  mov     [rbp+57h+var_9C], ax
0x18001803a  mov     r8d, 0CCh; uID
0x180018040  mov     rdx, cs:hInstance; hInstance
0x180018047  lea     rcx, [rbp+57h+var_60]; this
0x18001804b  call    ?LoadStringResource@CBsString@@QEAAJPEAUHINSTANCE__@@I@Z; CBsString::LoadStringResource(HINSTANCE__ *,uint)
0x180018050  mov     ebx, eax
0x180018052  mov     [rbp+57h+var_A0], eax
0x180018055  test    eax, eax
0x180018057  mov     eax, 502h
0x18001805c  js      loc_180017F10
0x180018062  mov     [rbp+57h+var_9C], ax
0x180018066  mov     rcx, [rdi+2C0h]
0x18001806d  mov     rax, [rcx]
0x180018070  mov     r9d, [rdi+0BCh]
0x180018077  shr     r9d, 1
0x18001807a  not     r9d
0x18001807d  and     r9d, 1
0x180018081  lea     rdx, [rbp+57h+var_40]
0x180018085  mov     [rsp+100h+var_C8], rdx
0x18001808a  mov     [rsp+100h+var_D0], r15d
0x18001808f  mov     [rsp+100h+var_D8], r15
0x180018094  mov     dword ptr [rsp+100h+var_E0], 7
0x18001809c  mov     r8, [rbp+57h+var_60]
0x1800180a0  mov     edx, 0Fh
0x1800180a5  mov     rax, [rax+18h]
0x1800180a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180ae  mov     ebx, eax
0x1800180b0  mov     [rbp+57h+var_A0], eax
0x1800180b3  test    eax, eax
0x1800180b5  mov     eax, 50Eh
0x1800180ba  js      loc_180017F10
0x1800180c0  mov     [rbp+57h+var_9C], ax
0x1800180c4  movups  xmm0, [rbp+57h+var_40]
0x1800180c8  movdqu  xmmword ptr [r14], xmm0
0x1800180cd  cmp     [rbp+57h+pv], r15
0x1800180d1  jz      short loc_18001810C
0x1800180d3  mov     edi, r15d
0x1800180d6  cmp     [rbp+57h+var_B0], r15d
0x1800180da  jbe     short loc_1800180FB
0x1800180dc  mov     ebx, edi
0x1800180de  mov     rcx, [rbp+57h+pv]
0x1800180e2  mov     rcx, [rcx+rbx*8]; pv
0x1800180e6  call    cs:__imp_CoTaskMemFree
0x1800180ec  mov     rax, [rbp+57h+pv]
0x1800180f0  mov     [rax+rbx*8], r15
0x1800180f4  inc     edi
0x1800180f6  cmp     edi, [rbp+57h+var_B0]
0x1800180f9  jb      short loc_1800180DC
0x1800180fb  mov     rcx, [rbp+57h+pv]; pv
0x1800180ff  call    cs:__imp_CoTaskMemFree
0x180018105  mov     [rbp+57h+pv], r15
0x180018109  mov     ebx, [rbp+57h+var_A0]
0x18001810c  test    rsi, rsi
0x18001810f  jz      short loc_18001812B
0x180018111  mov     rax, [rsi]
0x180018114  mov     rcx, rsi
0x180018117  mov     rax, [rax+60h]
0x18001811b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018120  mov     ebx, [rbp+57h+var_A0]
0x180018123  test    ebx, ebx
0x180018125  cmovns  ebx, eax
0x180018128  mov     [rbp+57h+var_A0], ebx
0x18001812b  lea     rcx, [rbp+57h+var_60]; this
0x18001812f  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180018134  lea     rcx, [rbp+57h+var_A0]; this
0x180018138  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001813d  mov     eax, ebx
0x18001813f  mov     rcx, [rbp+57h+var_30]
0x180018143  xor     rcx, rsp; StackCookie
0x180018146  call    __security_check_cookie
0x18001814b  mov     rbx, [rsp+100h+arg_18]
0x180018153  add     rsp, 0E0h
0x18001815a  pop     r15
0x18001815c  pop     r14
0x18001815e  pop     rdi
0x18001815f  pop     rsi
0x180018160  pop     rbp
0x180018161  retn
```
