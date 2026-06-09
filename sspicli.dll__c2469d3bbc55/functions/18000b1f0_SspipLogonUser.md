# SspipLogonUser

- ea: `0x18000b1f0`
- end: `0x18000b607`
- name: `SspipLogonUser`
- size: `1047`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x18000aaa0`
- `0x18000ab30`

## callees

- `0x18000b1f0`
- `0x180018db8`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x18000b365`
- `ntdll!NtQueryInformationThread` at `0x18000b365`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800223b1`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800223b1`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000b559`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000b559`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b318`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b318`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000b48b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000b48b`

## pseudocode

```c
NTSTATUS __fastcall SspipLogonUser(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        __int64 a5,
        int a6,
        __int64 a7,
        __int64 a8,
        _QWORD *a9,
        __int64 a10,
        __int64 a11,
        _QWORD *a12,
        _OWORD *a13,
        __int64 a14)
{
  __int64 v14; // rdi
  int v15; // r13d
  _DWORD *Value; // rax
  NTSTATUS result; // eax
  __int64 v20; // [rsp+A0h] [rbp-148h] BYREF
  __int64 v21; // [rsp+A8h] [rbp-140h] BYREF
  __int64 v22; // [rsp+B0h] [rbp-138h]
  __int64 v23; // [rsp+B8h] [rbp-130h]
  __int64 v24; // [rsp+C0h] [rbp-128h]
  __int64 v25; // [rsp+C8h] [rbp-120h]
  __int64 v26; // [rsp+D0h] [rbp-118h]
  __int64 v27; // [rsp+D8h] [rbp-110h]
  __int128 v28; // [rsp+E0h] [rbp-108h] BYREF
  __int64 v29; // [rsp+F0h] [rbp-F8h]
  __int64 v30; // [rsp+F8h] [rbp-F0h]
  _OWORD *v31; // [rsp+100h] [rbp-E8h]
  _QWORD *v32; // [rsp+108h] [rbp-E0h]
  _QWORD *v33; // [rsp+110h] [rbp-D8h]
  __int128 ThreadInformation; // [rsp+120h] [rbp-C8h] BYREF
  __int128 v35; // [rsp+130h] [rbp-B8h]
  __int128 v36; // [rsp+140h] [rbp-A8h]
  __int128 v37; // [rsp+150h] [rbp-98h] BYREF
  __int128 v38; // [rsp+160h] [rbp-88h] BYREF
  __int128 v39; // [rsp+170h] [rbp-78h]
  __int128 v40; // [rsp+180h] [rbp-68h]
  GUID ActivityId; // [rsp+190h] [rbp-58h] BYREF

  v27 = a2;
  v30 = a1;
  v31 = a13;
  v25 = a7;
  v26 = a8;
  v32 = a9;
  v23 = a10;
  v22 = a11;
  v33 = a12;
  v24 = a14;
  v37 = 0;
  v28 = 0;
  v29 = 0;
  v14 = 0;
  v15 = 0;
  v20 = 0;
  v21 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  if ( (DllState & 0x20000000) == 0 )
  {
    Value = TlsGetValue(SecTlsIP);
    v14 = (__int64)Value;
    if ( Value )
      v15 = Value[8];
  }
  ThreadInformation = 0;
  v35 = 0;
  v36 = 0;
  result = NtQueryInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadBasicInformation, &ThreadInformation, 0x30u, 0);
  if ( result >= 0 )
  {
    v37 = v35;
    LODWORD(v28) = a6;
    *((_QWORD *)&v28 + 1) = a5;
    v29 = a5;
    if ( SecpLsaInprocDispatch )
    {
      result = (*(__int64 (__fastcall **)(_QWORD, __int128 *, __int64, _QWORD, int, __int128 *, __int64, __int64, int, __int64, __int64, __int64 *, __int64, __int64, __int64 *, __int128 *))(SecpLsaInprocDispatch + 48))(
                 0,
                 &v37,
                 v27,
                 a3,
                 a4,
                 &v28,
                 v26,
                 v25,
                 v15,
                 v14,
                 v24,
                 &v20,
                 v23,
                 v22,
                 &v21,
                 &v38);
    }
    else
    {
      ActivityId = 0;
      EventActivityIdControl(1u, &ActivityId);
      result = SspirLogonUser2(
                 v30,
                 (unsigned int)&ActivityId,
                 (unsigned int)&v37,
                 v27,
                 a3,
                 a4,
                 (__int64)&v28,
                 v26,
                 v25,
                 v15,
                 v14,
                 v24,
                 (__int64)&v20,
                 v23,
                 v22,
                 (__int64)&v21,
                 (__int64)&v38);
    }
    if ( result >= 0 )
    {
      *a9 = v20;
      *a12 = v21;
      *a13 = v38;
      a13[1] = v39;
      a13[2] = v40;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000b1f0  mov     r11, rsp
0x18000b1f3  push    rbx
0x18000b1f4  push    rsi
0x18000b1f5  push    rdi
0x18000b1f6  push    r12
0x18000b1f8  push    r13
0x18000b1fa  push    r14
0x18000b1fc  push    r15
0x18000b1fe  sub     rsp, 1B0h
0x18000b205  mov     rax, cs:__security_cookie
0x18000b20c  xor     rax, rsp
0x18000b20f  mov     [rsp+1E8h+var_48], rax
0x18000b217  mov     [rsp+1E8h+var_158], r9d
0x18000b21f  mov     [rsp+1E8h+var_154], r8d
0x18000b227  mov     [rsp+1E8h+var_110], rdx
0x18000b22f  mov     [rsp+1E8h+var_F0], rcx
0x18000b237  mov     rsi, [rsp+1E8h+arg_60]
0x18000b23f  mov     [rsp+1E8h+var_E8], rsi
0x18000b247  mov     r12, [rsp+1E8h+arg_20]
0x18000b24f  mov     rax, [rsp+1E8h+arg_30]
0x18000b257  mov     [rsp+1E8h+var_120], rax
0x18000b25f  mov     rax, [rsp+1E8h+arg_38]
0x18000b267  mov     [rsp+1E8h+var_118], rax
0x18000b26f  mov     r14, [rsp+1E8h+arg_40]
0x18000b277  mov     [rsp+1E8h+var_E0], r14
0x18000b27f  mov     rax, [rsp+1E8h+arg_48]
0x18000b287  mov     [rsp+1E8h+var_130], rax
0x18000b28f  mov     rax, [rsp+1E8h+arg_50]
0x18000b297  mov     [rsp+1E8h+var_138], rax
0x18000b29f  mov     r15, [rsp+1E8h+arg_58]
0x18000b2a7  mov     [rsp+1E8h+var_D8], r15
0x18000b2af  mov     rbx, rsi
0x18000b2b2  mov     rax, [rsp+1E8h+arg_68]
0x18000b2ba  mov     [rsp+1E8h+var_128], rax
0x18000b2c2  xorps   xmm0, xmm0
0x18000b2c5  movups  [rsp+1E8h+var_98], xmm0
0x18000b2cd  xorps   xmm1, xmm1
0x18000b2d0  xor     eax, eax
0x18000b2d2  movups  [rsp+1E8h+var_108], xmm1
0x18000b2da  mov     [r11-0F8h], rax
0x18000b2e1  xor     edi, edi
0x18000b2e3  mov     r13d, edi
0x18000b2e6  mov     [r11-148h], rdi
0x18000b2ed  mov     [r11-140h], rdi
0x18000b2f4  movups  [rsp+1E8h+var_88], xmm0
0x18000b2fc  movups  xmmword ptr [r11-78h], xmm0
0x18000b301  movups  xmmword ptr [r11-68h], xmm0
0x18000b306  test    cs:DllState, 20000000h
0x18000b310  jnz     short loc_18000B32A
0x18000b312  mov     ecx, cs:SecTlsIP; dwTlsIndex
0x18000b318  call    cs:__imp_TlsGetValue
0x18000b31e  mov     rdi, rax
0x18000b321  test    rax, rax
0x18000b324  jz      short loc_18000B32A
0x18000b326  mov     r13d, [rax+20h]
0x18000b32a  xorps   xmm0, xmm0
0x18000b32d  movups  [rsp+1E8h+ThreadInformation], xmm0
0x18000b335  movups  [rsp+1E8h+var_B8], xmm0
0x18000b33d  movups  [rsp+1E8h+var_A8], xmm0
0x18000b345  mov     [rsp+1E8h+ReturnLength], 0; ReturnLength
0x18000b34e  mov     r9d, 30h ; '0'; ThreadInformationLength
0x18000b354  lea     r8, [rsp+1E8h+ThreadInformation]; ThreadInformation
0x18000b35c  xor     edx, edx; ThreadInformationClass
0x18000b35e  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000b365  call    cs:__imp_NtQueryInformationThread
0x18000b36b  test    eax, eax
0x18000b36d  js      loc_18000B5E4
0x18000b373  mov     rax, qword ptr [rsp+1E8h+var_B8]
0x18000b37b  mov     qword ptr [rsp+1E8h+var_98], rax
0x18000b383  mov     rax, qword ptr [rsp+1E8h+var_B8+8]
0x18000b38b  mov     qword ptr [rsp+1E8h+var_98+8], rax
0x18000b393  mov     eax, [rsp+1E8h+arg_28]
0x18000b39a  mov     dword ptr [rsp+1E8h+var_108], eax
0x18000b3a1  mov     qword ptr [rsp+1E8h+var_108+8], r12
0x18000b3a9  mov     [rsp+1E8h+var_F8], r12
0x18000b3b1  mov     rax, cs:SecpLsaInprocDispatch
0x18000b3b8  test    rax, rax
0x18000b3bb  jz      loc_18000B473
0x18000b3c1  lea     rcx, [rsp+1E8h+var_88]
0x18000b3c9  mov     [rsp+1E8h+var_170], rcx
0x18000b3ce  lea     rcx, [rsp+1E8h+var_140]
0x18000b3d6  mov     [rsp+1E8h+var_178], rcx
0x18000b3db  mov     rcx, [rsp+1E8h+var_138]
0x18000b3e3  mov     [rsp+1E8h+var_180], rcx
0x18000b3e8  mov     rcx, [rsp+1E8h+var_130]
0x18000b3f0  mov     [rsp+1E8h+var_188], rcx
0x18000b3f5  lea     rcx, [rsp+1E8h+var_148]
0x18000b3fd  mov     [rsp+1E8h+var_190], rcx
0x18000b402  mov     rcx, [rsp+1E8h+var_128]
0x18000b40a  mov     [rsp+1E8h+var_198], rcx
0x18000b40f  mov     [rsp+1E8h+var_1A0], rdi
0x18000b414  mov     dword ptr [rsp+1E8h+var_1A8], r13d
0x18000b419  mov     rcx, [rsp+1E8h+var_120]
0x18000b421  mov     [rsp+1E8h+var_1B0], rcx
0x18000b426  mov     rcx, [rsp+1E8h+var_118]
0x18000b42e  mov     [rsp+1E8h+var_1B8], rcx
0x18000b433  lea     rcx, [rsp+1E8h+var_108]
0x18000b43b  mov     [rsp+1E8h+var_1C0], rcx
0x18000b440  mov     ecx, [rsp+1E8h+var_158]
0x18000b447  mov     dword ptr [rsp+1E8h+ReturnLength], ecx
0x18000b44b  mov     r9d, [rsp+1E8h+var_154]
0x18000b453  mov     r8, [rsp+1E8h+var_110]
0x18000b45b  lea     rdx, [rsp+1E8h+var_98]
0x18000b463  xor     ecx, ecx
0x18000b465  mov     rax, [rax+30h]
0x18000b469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b46e  jmp     loc_18000B581
0x18000b473  xorps   xmm0, xmm0
0x18000b476  movups  xmmword ptr [rsp+1E8h+ActivityId.Data1], xmm0
0x18000b47e  lea     rdx, [rsp+1E8h+ActivityId]; ActivityId
0x18000b486  mov     ecx, 1; ControlCode
0x18000b48b  call    cs:__imp_EventActivityIdControl
0x18000b491  lea     rax, [rsp+1E8h+var_88]
0x18000b499  mov     [rsp+1E8h+var_168], rax
0x18000b4a1  lea     rax, [rsp+1E8h+var_140]
0x18000b4a9  mov     [rsp+1E8h+var_170], rax
0x18000b4ae  mov     rcx, [rsp+1E8h+var_138]
0x18000b4b6  mov     [rsp+1E8h+var_178], rcx
0x18000b4bb  mov     rcx, [rsp+1E8h+var_130]
0x18000b4c3  mov     [rsp+1E8h+var_180], rcx
0x18000b4c8  lea     rax, [rsp+1E8h+var_148]
0x18000b4d0  mov     [rsp+1E8h+var_188], rax
0x18000b4d5  mov     rcx, [rsp+1E8h+var_128]
0x18000b4dd  mov     [rsp+1E8h+var_190], rcx
0x18000b4e2  mov     [rsp+1E8h+var_198], rdi
0x18000b4e7  mov     dword ptr [rsp+1E8h+var_1A0], r13d
0x18000b4ec  mov     rcx, [rsp+1E8h+var_120]
0x18000b4f4  mov     [rsp+1E8h+var_1A8], rcx
0x18000b4f9  mov     rcx, [rsp+1E8h+var_118]
0x18000b501  mov     [rsp+1E8h+var_1B0], rcx
0x18000b506  lea     rax, [rsp+1E8h+var_108]
0x18000b50e  mov     [rsp+1E8h+var_1B8], rax
0x18000b513  mov     ecx, [rsp+1E8h+var_158]
0x18000b51a  mov     dword ptr [rsp+1E8h+var_1C0], ecx
0x18000b51e  mov     ecx, [rsp+1E8h+var_154]
0x18000b525  mov     dword ptr [rsp+1E8h+ReturnLength], ecx
0x18000b529  mov     r9, [rsp+1E8h+var_110]
0x18000b531  lea     r8, [rsp+1E8h+var_98]
0x18000b539  lea     rdx, [rsp+1E8h+ActivityId]
0x18000b541  mov     rcx, [rsp+1E8h+var_F0]
0x18000b549  call    SspirLogonUser2
0x18000b54e  mov     [rsp+1E8h+var_150], eax
0x18000b555  jmp     short loc_18000B581
0x18000b557  mov     ecx, eax; Status
0x18000b559  call    cs:__imp_I_RpcMapWin32Status
0x18000b55f  mov     [rsp+1E8h+var_150], eax
0x18000b566  mov     rsi, [rsp+1E8h+var_E8]
0x18000b56e  mov     r14, [rsp+1E8h+var_E0]
0x18000b576  mov     r15, [rsp+1E8h+var_D8]
0x18000b57e  mov     rbx, rsi
0x18000b581  test    eax, eax
0x18000b583  js      short loc_18000B5E4
0x18000b585  mov     rax, [rsp+1E8h+var_148]
0x18000b58d  mov     [r14], rax
0x18000b590  mov     rax, [rsp+1E8h+var_140]
0x18000b598  mov     [r15], rax
0x18000b59b  mov     rax, qword ptr [rsp+1E8h+var_88]
0x18000b5a3  mov     [rsi], rax
0x18000b5a6  mov     rax, qword ptr [rsp+1E8h+var_88+8]
0x18000b5ae  mov     [rbx+8], rax
0x18000b5b2  mov     rax, [rsp+1E8h+var_78]
0x18000b5ba  mov     [rbx+10h], rax
0x18000b5be  mov     rax, [rsp+1E8h+var_70]
0x18000b5c6  mov     [rbx+18h], rax
0x18000b5ca  mov     rax, [rsp+1E8h+var_68]
0x18000b5d2  mov     [rbx+20h], rax
0x18000b5d6  mov     rax, [rsp+1E8h+var_60]
0x18000b5de  mov     [rbx+28h], rax
0x18000b5e2  xor     eax, eax
0x18000b5e4  mov     rcx, [rsp+1E8h+var_48]
0x18000b5ec  xor     rcx, rsp; StackCookie
0x18000b5ef  call    __security_check_cookie
0x18000b5f4  add     rsp, 1B0h
0x18000b5fb  pop     r15
0x18000b5fd  pop     r14
0x18000b5ff  pop     r13
0x18000b601  pop     r12
0x18000b603  pop     rdi
0x18000b604  pop     rsi
0x18000b605  pop     rbx
0x18000b606  retn
0x1800223a0  push    rbp
0x1800223a2  sub     rsp, 90h
0x1800223a9  mov     rbp, rdx
0x1800223ac  mov     rcx, [rcx]
0x1800223af  mov     ecx, [rcx]; ExceptionCode
0x1800223b1  call    cs:__imp_I_RpcExceptionFilter
0x1800223b7  nop
0x1800223b8  add     rsp, 90h
0x1800223bf  pop     rbp
0x1800223c0  retn
```
