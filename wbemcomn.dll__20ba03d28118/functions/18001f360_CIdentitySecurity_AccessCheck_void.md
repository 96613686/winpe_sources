# CIdentitySecurity::AccessCheck(void)

- ea: `0x18001f360`
- end: `0x18001f4af`
- name: `?AccessCheck@CIdentitySecurity@@QEAAHXZ`
- size: `335`
- prototype: `_BOOL8 __fastcall(CIdentitySecurity *this)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000ab30`
- `0x18001cd60`
- `0x18001f360`
- `0x180024eb0`
- `0x1800284c0`
- `0x1800307ec`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18001f3ba`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18001f3ba`

## pseudocode

```c
_BOOL8 __fastcall CIdentitySecurity::AccessCheck(CIdentitySecurity *this)
{
  void *v3; // rbx
  void *v4; // rdi
  int SidFromThreadOrProcess; // r14d
  void *v6; // rbx
  BOOL v7; // ebx
  void *v8; // [rsp+20h] [rbp-10h] BYREF
  int v9; // [rsp+28h] [rbp-8h]
  int v10; // [rsp+2Ch] [rbp-4h]
  void *ppInterface; // [rsp+60h] [rbp+30h] BYREF
  void *v12; // [rsp+68h] [rbp+38h]
  void *v13; // [rsp+70h] [rbp+40h]

  if ( *((_BYTE *)this + 32) && !CIdentitySecurity::EncryptedCall(this) )
    return 0;
  v3 = 0;
  v8 = 0;
  v9 = 6;
  v10 = 8;
  if ( NtCurrentTeb()->IsImpersonating || (ppInterface = 0, CoGetCallContext(&IID_IServerSecurity, &ppInterface)) )
  {
    SidFromThreadOrProcess = CIdentitySecurity::GetSidFromThreadOrProcess(this, (struct CNtSid *)&v8);
  }
  else
  {
    v4 = ppInterface;
    v12 = ppInterface;
    if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppInterface + 48LL))(ppInterface) )
    {
      SidFromThreadOrProcess = CIdentitySecurity::GetSidFromThreadOrProcess(this, (struct CNtSid *)&v8);
    }
    else
    {
      if ( (*(int (__fastcall **)(void *))(*(_QWORD *)ppInterface + 32LL))(ppInterface) < 0 )
      {
        (*(void (__fastcall **)(void *))(*(_QWORD *)v4 + 16LL))(v4);
LABEL_15:
        CMUILocale::_Free(v3);
        return 0;
      }
      v6 = ppInterface;
      v13 = ppInterface;
      SidFromThreadOrProcess = CIdentitySecurity::GetSidFromThreadOrProcess(this, (struct CNtSid *)&v8);
       IServerSecurity::`vcall'{40,{flat}}((__int64)v6);
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v4 + 16LL))(v4);
  }
  if ( SidFromThreadOrProcess < 0 )
  {
    v3 = v8;
    goto LABEL_15;
  }
  v7 = (unsigned int)CNtSid::operator==((__int64)&v8, (__int64)this)
    || (unsigned int)CNtSid::operator==((__int64)&v8, (__int64)this + 16);
  CMUILocale::_Free(v8);
  return v7;
}

```

## disassembly

```asm
0x18001f360  push    rbp
0x18001f362  push    rbx
0x18001f363  push    rsi
0x18001f364  push    rdi
0x18001f365  push    r14
0x18001f367  mov     rbp, rsp
0x18001f36a  sub     rsp, 30h
0x18001f36e  mov     rsi, rcx
0x18001f371  cmp     byte ptr [rcx+20h], 0
0x18001f375  jz      short loc_18001F387
0x18001f377  call    ?EncryptedCall@CIdentitySecurity@@AEAA_NXZ; CIdentitySecurity::EncryptedCall(void)
0x18001f37c  test    al, al
0x18001f37e  jnz     short loc_18001F387
0x18001f380  xor     eax, eax
0x18001f382  jmp     loc_18001F4A4
0x18001f387  xor     ebx, ebx
0x18001f389  mov     [rbp+var_10], rbx
0x18001f38d  mov     [rbp+var_8], 6
0x18001f394  mov     [rbp+var_4], 8
0x18001f39b  mov     eax, gs:179Ch
0x18001f3a3  test    eax, eax
0x18001f3a5  jnz     loc_18001F44A
0x18001f3ab  mov     [rbp+ppInterface], rbx
0x18001f3af  lea     rdx, [rbp+ppInterface]; ppInterface
0x18001f3b3  lea     rcx, IID_IServerSecurity; riid
0x18001f3ba  call    cs:__imp_CoGetCallContext
0x18001f3c0  test    eax, eax
0x18001f3c2  jnz     loc_18001F44A
0x18001f3c8  mov     rdi, [rbp+ppInterface]
0x18001f3cc  mov     [rbp+arg_8], rdi
0x18001f3d0  mov     rcx, [rbp+ppInterface]
0x18001f3d4  mov     rax, [rcx]
0x18001f3d7  mov     rax, [rax+30h]
0x18001f3db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3e0  test    eax, eax
0x18001f3e2  jz      short loc_18001F404
0x18001f3e4  lea     rdx, [rbp+var_10]; struct CNtSid *
0x18001f3e8  mov     rcx, rsi; this
0x18001f3eb  call    ?GetSidFromThreadOrProcess@CIdentitySecurity@@AEAAJAEAVCNtSid@@@Z; CIdentitySecurity::GetSidFromThreadOrProcess(CNtSid &)
0x18001f3f0  mov     r14d, eax
0x18001f3f3  mov     rax, [rdi]
0x18001f3f6  mov     rcx, rdi
0x18001f3f9  mov     rax, [rax+10h]
0x18001f3fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f402  jmp     short loc_18001F459
0x18001f404  mov     rcx, [rbp+ppInterface]
0x18001f408  mov     rax, [rcx]
0x18001f40b  mov     rax, [rax+20h]
0x18001f40f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f414  test    eax, eax
0x18001f416  jns     short loc_18001F429
0x18001f418  mov     rax, [rdi]
0x18001f41b  mov     rcx, rdi
0x18001f41e  mov     rax, [rax+10h]
0x18001f422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f427  jmp     short loc_18001F462
0x18001f429  mov     rbx, [rbp+ppInterface]
0x18001f42d  mov     [rbp+arg_10], rbx
0x18001f431  lea     rdx, [rbp+var_10]; struct CNtSid *
0x18001f435  mov     rcx, rsi; this
0x18001f438  call    ?GetSidFromThreadOrProcess@CIdentitySecurity@@AEAAJAEAVCNtSid@@@Z; CIdentitySecurity::GetSidFromThreadOrProcess(CNtSid &)
0x18001f43d  mov     r14d, eax
0x18001f440  mov     rcx, rbx
0x18001f443  call    ??_9IServerSecurity@@$BCI@AA; [thunk]: IServerSecurity::`vcall'{40,{flat}}
0x18001f448  jmp     short loc_18001F3F3
0x18001f44a  lea     rdx, [rbp+var_10]; struct CNtSid *
0x18001f44e  mov     rcx, rsi; this
0x18001f451  call    ?GetSidFromThreadOrProcess@CIdentitySecurity@@AEAAJAEAVCNtSid@@@Z; CIdentitySecurity::GetSidFromThreadOrProcess(CNtSid &)
0x18001f456  mov     r14d, eax
0x18001f459  test    r14d, r14d
0x18001f45c  jns     short loc_18001F46F
0x18001f45e  mov     rbx, [rbp+var_10]
0x18001f462  mov     rcx, rbx; void *
0x18001f465  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x18001f46a  jmp     loc_18001F380
0x18001f46f  mov     rdx, rsi
0x18001f472  lea     rcx, [rbp+var_10]
0x18001f476  call    ??8CNtSid@@QEAAHAEAV0@@Z; CNtSid::operator==(CNtSid &)
0x18001f47b  test    eax, eax
0x18001f47d  jnz     short loc_18001F494
0x18001f47f  lea     rdx, [rsi+10h]
0x18001f483  lea     rcx, [rbp+var_10]
0x18001f487  call    ??8CNtSid@@QEAAHAEAV0@@Z; CNtSid::operator==(CNtSid &)
0x18001f48c  test    eax, eax
0x18001f48e  jnz     short loc_18001F494
0x18001f490  xor     ebx, ebx
0x18001f492  jmp     short loc_18001F499
0x18001f494  mov     ebx, 1
0x18001f499  mov     rcx, [rbp+var_10]; void *
0x18001f49d  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x18001f4a2  mov     eax, ebx
0x18001f4a4  add     rsp, 30h
0x18001f4a8  pop     r14
0x18001f4aa  pop     rdi
0x18001f4ab  pop     rsi
0x18001f4ac  pop     rbx
0x18001f4ad  pop     rbp
0x18001f4ae  retn
```
