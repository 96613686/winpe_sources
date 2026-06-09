# CSdBackupImpl::_CreateSnapshots(ISdAsyncPriv *,_GUID *)

- ea: `0x180018874`
- end: `0x180018b75`
- name: `?_CreateSnapshots@CSdBackupImpl@@AEAAJPEAUISdAsyncPriv@@PEAU_GUID@@@Z`
- size: `769`
- prototype: `__int64 __fastcall(CSdBackupImpl *__hidden this, struct ISdAsyncPriv *, struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003f5f0`

## callees

- `0x1800178cc`
- `0x180018874`
- `0x180072e08`
- `0x180072f14`
- `0x18007351c`
- `0x18009e658`
- `0x18009f560`
- `0x1800cf5c0`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180018951`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180018951`
- `ole32!CoTaskMemFree` at `0x180018aec`
- `ole32!CoTaskMemFree` at `0x180018b0b`
- `ole32!CoTaskMemFree` at `0x180018aec`
- `ole32!CoTaskMemFree` at `0x180018b0b`

## string_xrefs

- `0x1800188ac`: `CSdBackupImpl::_CreateSnapshots`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v17, "CSdBackupImpl::_CreateSnapshots", 0x4D5u, 0);
  v23 = GUID_NULL;
  v20 = 0;
  pv = 0;
  v15 = 0;
  v21[0] = qword_1800EE510;
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
  v22 = xmmword_1800E1DA8;
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
  v22 = xmmword_1800E1DA8;
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
0x180018874  mov     [rsp-8+arg_18], rbx
0x180018879  push    rbp
0x18001887a  push    rsi
0x18001887b  push    rdi
0x18001887c  push    r14
0x18001887e  push    r15
0x180018880  lea     rbp, [rsp-37h]
0x180018885  sub     rsp, 0E0h
0x18001888c  mov     rax, cs:__security_cookie
0x180018893  xor     rax, rsp
0x180018896  mov     [rbp+57h+var_30], rax
0x18001889a  mov     r14, r8
0x18001889d  mov     rsi, rdx
0x1800188a0  mov     rdi, rcx
0x1800188a3  xor     r9d, r9d; unsigned __int16
0x1800188a6  mov     r8d, 4D5h; unsigned __int16
0x1800188ac  lea     rdx, aCsdbackupimplC_8; "CSdBackupImpl::_CreateSnapshots"
0x1800188b3  lea     rcx, [rbp+57h+var_A0]; this
0x1800188b7  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800188bc  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800188c3  movdqu  [rbp+57h+var_40], xmm0
0x1800188c8  xor     r15d, r15d
0x1800188cb  mov     [rbp+57h+var_68], r15d
0x1800188cf  mov     [rbp+57h+pv], r15
0x1800188d3  mov     [rbp+57h+var_B0], r15d
0x1800188d7  lea     rax, qword_1800EE510
0x1800188de  mov     [rbp+57h+var_60], rax
0x1800188e2  mov     [rbp+57h+var_58], r15
0x1800188e6  test    r14, r14
0x1800188e9  jz      short loc_1800188FE
0x1800188eb  lea     ecx, [r15+10h]
0x1800188ef  mov     rax, r14
0x1800188f2  mov     [rax], r15b
0x1800188f5  inc     rax
0x1800188f8  sub     rcx, 1
0x1800188fc  jnz     short loc_1800188F2
0x1800188fe  mov     eax, 4E5h
0x180018903  test    rsi, rsi
0x180018906  jnz     short loc_180018919
0x180018908  mov     ebx, 80070057h
0x18001890d  mov     [rbp+57h+var_A0], ebx
0x180018910  mov     [rbp+57h+var_9A], ax
0x180018914  jmp     loc_180018AD3
0x180018919  mov     [rbp+57h+var_A0], r15d
0x18001891d  mov     [rbp+57h+var_9C], ax
0x180018921  mov     [rsp+100h+var_E0], r15; unsigned __int16 **
0x180018926  xor     r9d, r9d; unsigned int
0x180018929  mov     r8d, 4E21h; unsigned int
0x18001892f  mov     rdx, cs:hInstance; HINSTANCE
0x180018936  lea     rcx, [rbp+57h+var_A0]; this
0x18001893a  call    ?_SetContextHelper@CSxFunctionTracer@@AEAAJPEAUHINSTANCE__@@KKPEAPEBG@Z; CSxFunctionTracer::_SetContextHelper(HINSTANCE__ *,ulong,ulong,ushort const * *)
0x18001893f  mov     ebx, eax
0x180018941  mov     [rbp+57h+var_A0], eax
0x180018944  test    eax, eax
0x180018946  mov     eax, 4E7h
0x18001894b  js      short loc_180018910
0x18001894d  mov     [rbp+57h+var_9C], ax
0x180018951  call    cs:__imp_RevertToSelf
0x180018958  nop     dword ptr [rax+rax+00h]
0x18001895d  lea     r9, [rbp+57h+pv]; unsigned __int16 ***
0x180018961  lea     r8, [rbp+57h+var_B0]; unsigned int *
0x180018965  mov     rdx, rsi; struct ISdAsyncPriv *
0x180018968  mov     rcx, rdi; this
0x18001896b  call    ?_BuildVolumePathsForSnapshot@CSdBackupImpl@@AEAAJPEAUISdAsyncPriv@@PEAKPEAPEAPEAG@Z; CSdBackupImpl::_BuildVolumePathsForSnapshot(ISdAsyncPriv *,ulong *,ushort * * *)
0x180018970  mov     ebx, eax
0x180018972  mov     [rbp+57h+var_A0], eax
0x180018975  test    eax, eax
0x180018977  mov     eax, 4EDh
0x18001897c  js      short loc_180018910
0x18001897e  mov     [rbp+57h+var_9C], ax
0x180018982  mov     rcx, [rdi+160h]
0x180018989  mov     rax, [rcx]
0x18001898c  lea     rdx, [rbp+57h+var_68]
0x180018990  mov     rax, [rax+0D0h]
0x180018997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001899c  mov     ebx, eax
0x18001899e  mov     [rbp+57h+var_A0], eax
0x1800189a1  test    eax, eax
0x1800189a3  mov     eax, 4EFh
0x1800189a8  js      loc_180018910
0x1800189ae  mov     [rbp+57h+var_9C], ax
0x1800189b2  mov     rcx, [rdi+2C0h]
0x1800189b9  movups  xmm0, cs:xmmword_1800E1DA8
0x1800189c0  movdqu  [rbp+57h+var_50], xmm0
0x1800189c5  mov     rax, [rcx]
0x1800189c8  mov     rdx, [rbp+57h+pv]
0x1800189cc  mov     [rsp+100h+var_E0], rdx
0x1800189d1  mov     r9d, [rbp+57h+var_B0]
0x1800189d5  mov     r8d, 1
0x1800189db  lea     rdx, [rbp+57h+var_50]
0x1800189df  mov     rax, [rax+58h]
0x1800189e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189e8  mov     ebx, eax
0x1800189ea  mov     [rbp+57h+var_A0], eax
0x1800189ed  test    eax, eax
0x1800189ef  mov     eax, 4FCh
0x1800189f4  js      loc_180018910
0x1800189fa  mov     [rbp+57h+var_9C], ax
0x1800189fe  mov     rcx, [rdi+2C0h]
0x180018a05  movups  xmm0, cs:xmmword_1800E1DA8
0x180018a0c  movdqu  [rbp+57h+var_50], xmm0
0x180018a11  mov     rax, [rcx]
0x180018a14  mov     r8d, 5265C00h
0x180018a1a  lea     rdx, [rbp+57h+var_50]
0x180018a1e  mov     rax, [rax+0F8h]
0x180018a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a2a  mov     ebx, eax
0x180018a2c  mov     [rbp+57h+var_A0], eax
0x180018a2f  test    eax, eax
0x180018a31  mov     eax, 4FFh
0x180018a36  js      loc_180018910
0x180018a3c  mov     [rbp+57h+var_9C], ax
0x180018a40  mov     r8d, 0CCh; uID
0x180018a46  mov     rdx, cs:hInstance; hInstance
0x180018a4d  lea     rcx, [rbp+57h+var_60]; this
0x180018a51  call    ?LoadStringResource@CBsString@@QEAAJPEAUHINSTANCE__@@I@Z; CBsString::LoadStringResource(HINSTANCE__ *,uint)
0x180018a56  mov     ebx, eax
0x180018a58  mov     [rbp+57h+var_A0], eax
0x180018a5b  test    eax, eax
0x180018a5d  mov     eax, 502h
0x180018a62  js      loc_180018910
0x180018a68  mov     [rbp+57h+var_9C], ax
0x180018a6c  mov     rcx, [rdi+2C0h]
0x180018a73  mov     rax, [rcx]
0x180018a76  mov     r9d, [rdi+0BCh]
0x180018a7d  shr     r9d, 1
0x180018a80  not     r9d
0x180018a83  and     r9d, 1
0x180018a87  lea     rdx, [rbp+57h+var_40]
0x180018a8b  mov     [rsp+100h+var_C8], rdx
0x180018a90  mov     [rsp+100h+var_D0], r15d
0x180018a95  mov     [rsp+100h+var_D8], r15
0x180018a9a  mov     dword ptr [rsp+100h+var_E0], 7
0x180018aa2  mov     r8, [rbp+57h+var_60]
0x180018aa6  mov     edx, 0Fh
0x180018aab  mov     rax, [rax+18h]
0x180018aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ab4  mov     ebx, eax
0x180018ab6  mov     [rbp+57h+var_A0], eax
0x180018ab9  test    eax, eax
0x180018abb  mov     eax, 50Eh
0x180018ac0  js      loc_180018910
0x180018ac6  mov     [rbp+57h+var_9C], ax
0x180018aca  movups  xmm0, [rbp+57h+var_40]
0x180018ace  movdqu  xmmword ptr [r14], xmm0
0x180018ad3  cmp     [rbp+57h+pv], r15
0x180018ad7  jz      short loc_180018B1E
0x180018ad9  mov     edi, r15d
0x180018adc  cmp     [rbp+57h+var_B0], r15d
0x180018ae0  jbe     short loc_180018B07
0x180018ae2  mov     ebx, edi
0x180018ae4  mov     rcx, [rbp+57h+pv]
0x180018ae8  mov     rcx, [rcx+rbx*8]; pv
0x180018aec  call    cs:__imp_CoTaskMemFree
0x180018af3  nop     dword ptr [rax+rax+00h]
0x180018af8  mov     rax, [rbp+57h+pv]
0x180018afc  mov     [rax+rbx*8], r15
0x180018b00  inc     edi
0x180018b02  cmp     edi, [rbp+57h+var_B0]
0x180018b05  jb      short loc_180018AE2
0x180018b07  mov     rcx, [rbp+57h+pv]; pv
0x180018b0b  call    cs:__imp_CoTaskMemFree
0x180018b12  nop     dword ptr [rax+rax+00h]
0x180018b17  mov     [rbp+57h+pv], r15
0x180018b1b  mov     ebx, [rbp+57h+var_A0]
0x180018b1e  test    rsi, rsi
0x180018b21  jz      short loc_180018B3D
0x180018b23  mov     rax, [rsi]
0x180018b26  mov     rcx, rsi
0x180018b29  mov     rax, [rax+60h]
0x180018b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b32  mov     ebx, [rbp+57h+var_A0]
0x180018b35  test    ebx, ebx
0x180018b37  cmovns  ebx, eax
0x180018b3a  mov     [rbp+57h+var_A0], ebx
0x180018b3d  lea     rcx, [rbp+57h+var_60]; this
0x180018b41  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180018b46  lea     rcx, [rbp+57h+var_A0]; this
0x180018b4a  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180018b4f  mov     eax, ebx
0x180018b51  mov     rcx, [rbp+57h+var_30]
0x180018b55  xor     rcx, rsp; StackCookie
0x180018b58  call    __security_check_cookie
0x180018b5d  mov     rbx, [rsp+100h+arg_18]
0x180018b65  add     rsp, 0E0h
0x180018b6c  pop     r15
0x180018b6e  pop     r14
0x180018b70  pop     rdi
0x180018b71  pop     rsi
0x180018b72  pop     rbp
0x180018b73  retn
```
