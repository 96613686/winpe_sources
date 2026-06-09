# ShadowAdminAccount::CreateShadowAdminAccountSerialized(void)

- ea: `0x180091e7c`
- end: `0x180092037`
- name: `?CreateShadowAdminAccountSerialized@ShadowAdminAccount@@AEAAJXZ`
- size: `443`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180091c80`

## callees

- `0x180027e24`
- `0x1800372ac`
- `0x180091598`
- `0x180091e7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180091f4e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180091f4e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180091eda`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180091eda`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180091f03`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180091f03`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180091fbe`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180091fbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180091eef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180091eef`

## pseudocode

```c
__int64 __fastcall ShadowAdminAccount::CreateShadowAdminAccountSerialized(RTL_SRWLOCK *this)
{
  int Ptr; // ebx
  PUNICODE_STRING v3; // rcx
  int v5; // r14d
  DWORD *v6; // rsi
  __int64 v7; // rdx
  __int64 v8; // r9
  HANDLE EventW; // rax
  int ShadowAdminAccount; // eax
  DWORD v11; // eax

  if ( this[9].Ptr )
  {
    Ptr = 0;
LABEL_3:
    v3 = WPP_GLOBAL_Control;
    goto LABEL_4;
  }
  v5 = 0;
  AcquireSRWLockExclusive(this + 13);
  v6 = (DWORD *)&this[14];
  if ( this[9].Ptr )
    goto LABEL_10;
  if ( !*v6 )
  {
    *v6 = GetCurrentThreadId();
    v5 = 1;
LABEL_10:
    Ptr = 0;
    goto LABEL_11;
  }
  if ( this[15].Ptr )
    goto LABEL_10;
  EventW = CreateEventW(0, 1, 0, 0);
  this[15].Ptr = EventW;
  if ( EventW )
    goto LABEL_10;
  Ptr = -1073741801;
LABEL_11:
  ReleaseSRWLockExclusive(this + 13);
  if ( Ptr >= 0 )
  {
    if ( this[9].Ptr )
      goto LABEL_3;
    if ( v5 )
    {
      ShadowAdminAccount = ShadowAdminAccount::CreateShadowAdminAccount((PCWSTR *)this);
      *v6 = 0;
      Ptr = ShadowAdminAccount;
      if ( ShadowAdminAccount >= 0 )
        goto LABEL_3;
      v3 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) != 0
        && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      {
        v7 = 83;
        v8 = (unsigned int)ShadowAdminAccount;
        goto LABEL_16;
      }
    }
    else
    {
      v11 = WaitForSingleObject(this[15].Ptr, 0xFFFFFFFF);
      if ( v11 )
      {
        v3 = WPP_GLOBAL_Control;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) != 0
          && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 84, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids, v11);
          v3 = WPP_GLOBAL_Control;
        }
        Ptr = -1073741801;
      }
      else
      {
        Ptr = (int)this[16].Ptr;
        if ( Ptr >= 0 )
          goto LABEL_3;
        v3 = WPP_GLOBAL_Control;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) != 0
          && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
        {
          v7 = 85;
          goto LABEL_15;
        }
      }
    }
  }
  else
  {
    v3 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) != 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      v7 = 82;
LABEL_15:
      v8 = (unsigned int)Ptr;
LABEL_16:
      WPP_SF_d(v3[3].Buffer, v7, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids, v8);
      goto LABEL_3;
    }
  }
LABEL_4:
  if ( (*(_DWORD *)(&v3[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(v3[3].Buffer, 86, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids, (unsigned int)Ptr, Ptr);
  return (unsigned int)Ptr;
}

```

## disassembly

```asm
0x180091e7c  push    rbx
0x180091e7e  push    rbp
0x180091e7f  push    rsi
0x180091e80  push    rdi
0x180091e81  push    r12
0x180091e83  push    r14
0x180091e85  sub     rsp, 38h
0x180091e89  cmp     qword ptr [rcx+48h], 0
0x180091e8e  lea     r12, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids
0x180091e95  mov     rdi, rcx
0x180091e98  jz      short loc_180091ED3
0x180091e9a  xor     ebx, ebx
0x180091e9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180091ea3  test    dword ptr [rcx+44h], 20000h
0x180091eaa  jz      short loc_180091EC4
0x180091eac  mov     rcx, [rcx+38h]
0x180091eb0  mov     edx, 56h ; 'V'
0x180091eb5  mov     r9d, ebx
0x180091eb8  mov     [rsp+68h+var_48], ebx
0x180091ebc  mov     r8, r12
0x180091ebf  call    WPP_SF_Dd
0x180091ec4  mov     eax, ebx
0x180091ec6  add     rsp, 38h
0x180091eca  pop     r14
0x180091ecc  pop     r12
0x180091ece  pop     rdi
0x180091ecf  pop     rsi
0x180091ed0  pop     rbp
0x180091ed1  pop     rbx
0x180091ed2  retn
0x180091ed3  add     rcx, 68h ; 'h'; SRWLock
0x180091ed7  xor     r14d, r14d
0x180091eda  call    cs:__imp_AcquireSRWLockExclusive
0x180091ee0  lea     rsi, [rdi+70h]
0x180091ee4  cmp     [rdi+48h], r14
0x180091ee8  jnz     short loc_180091EFD
0x180091eea  cmp     [rsi], r14d
0x180091eed  jnz     short loc_180091F3C
0x180091eef  call    cs:__imp_GetCurrentThreadId
0x180091ef5  mov     [rsi], eax
0x180091ef7  mov     r14d, 1
0x180091efd  xor     ebx, ebx
0x180091eff  lea     rcx, [rdi+68h]; SRWLock
0x180091f03  call    cs:__imp_ReleaseSRWLockExclusive
0x180091f09  test    ebx, ebx
0x180091f0b  jns     short loc_180091F64
0x180091f0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180091f14  test    dword ptr [rcx+44h], 400h
0x180091f1b  jz      short loc_180091EA3
0x180091f1d  cmp     byte ptr [rcx+41h], 2
0x180091f21  jb      short loc_180091EA3
0x180091f23  mov     edx, 52h ; 'R'
0x180091f28  mov     r9d, ebx
0x180091f2b  mov     rcx, [rcx+38h]
0x180091f2f  mov     r8, r12
0x180091f32  call    WPP_SF_d
0x180091f37  jmp     loc_180091E9C
0x180091f3c  cmp     [rdi+78h], r14
0x180091f40  jnz     short loc_180091EFD
0x180091f42  xor     r9d, r9d; lpName
0x180091f45  xor     r8d, r8d; bInitialState
0x180091f48  xor     ecx, ecx; lpEventAttributes
0x180091f4a  lea     edx, [r9+1]; bManualReset
0x180091f4e  call    cs:__imp_CreateEventW
0x180091f54  mov     [rdi+78h], rax
0x180091f58  test    rax, rax
0x180091f5b  jnz     short loc_180091EFD
0x180091f5d  mov     ebx, 0C0000017h
0x180091f62  jmp     short loc_180091EFF
0x180091f64  cmp     qword ptr [rdi+48h], 0
0x180091f69  jnz     loc_180091E9C
0x180091f6f  test    r14d, r14d
0x180091f72  jz      short loc_180091FB7
0x180091f74  mov     rcx, rdi; this
0x180091f77  call    ?CreateShadowAdminAccount@ShadowAdminAccount@@AEAAJXZ; ShadowAdminAccount::CreateShadowAdminAccount(void)
0x180091f7c  mov     dword ptr [rsi], 0
0x180091f82  mov     ebx, eax
0x180091f84  test    eax, eax
0x180091f86  jns     loc_180091E9C
0x180091f8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180091f93  test    dword ptr [rcx+44h], 400h
0x180091f9a  jz      loc_180091EA3
0x180091fa0  cmp     byte ptr [rcx+41h], 2
0x180091fa4  jb      loc_180091EA3
0x180091faa  mov     edx, 53h ; 'S'
0x180091faf  mov     r9d, eax
0x180091fb2  jmp     loc_180091F2B
0x180091fb7  mov     rcx, [rdi+78h]; hHandle
0x180091fbb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180091fbe  call    cs:__imp_WaitForSingleObject
0x180091fc4  test    eax, eax
0x180091fc6  jnz     short loc_180091FFC
0x180091fc8  mov     ebx, [rdi+80h]
0x180091fce  test    ebx, ebx
0x180091fd0  jns     loc_180091E9C
0x180091fd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180091fdd  test    dword ptr [rcx+44h], 400h
0x180091fe4  jz      loc_180091EA3
0x180091fea  cmp     byte ptr [rcx+41h], 2
0x180091fee  jb      loc_180091EA3
0x180091ff4  lea     edx, [rax+55h]
0x180091ff7  jmp     loc_180091F28
0x180091ffc  mov     rcx, cs:WPP_GLOBAL_Control
0x180092003  test    dword ptr [rcx+44h], 400h
0x18009200a  jz      short loc_18009202D
0x18009200c  cmp     byte ptr [rcx+41h], 2
0x180092010  jb      short loc_18009202D
0x180092012  mov     rcx, [rcx+38h]
0x180092016  mov     edx, 54h ; 'T'
0x18009201b  mov     r9d, eax
0x18009201e  mov     r8, r12
0x180092021  call    WPP_SF_d
0x180092026  mov     rcx, cs:WPP_GLOBAL_Control
0x18009202d  mov     ebx, 0C0000017h
0x180092032  jmp     loc_180091EA3
```
