# WimFSFRemountWim

- ea: `0x14002dcc0`
- end: `0x14002dea9`
- name: `WimFSFRemountWim`
- size: `489`
- prototype: `EXPAND_STACK_CALLOUT`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x14000d9cc`
- `0x140011560`
- `0x1400119c0`
- `0x14002c53c`
- `0x14002d7f4`
- `0x14002da2c`
- `0x14002dcc0`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x14002de63`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14002de63`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002ddad`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002de3a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002ddad`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002de3a`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002dd9b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002de11`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002dd9b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002de11`
- `FLTMGR!FltReleaseContext` at `0x14002ddbc`
- `FLTMGR!FltReleaseContext` at `0x14002de49`
- `FLTMGR!FltReleaseContext` at `0x14002ddbc`
- `FLTMGR!FltReleaseContext` at `0x14002de49`

## pseudocode

```c
void __fastcall WimFSFRemountWim(_QWORD *Parameter)
{
  __int64 v1; // r14
  __int64 v3; // r15
  int v4; // eax
  struct _FAST_MUTEX *v5; // rdi
  char *v6; // rsi
  int v7; // eax
  __int64 v8; // rcx
  PFAST_MUTEX FastMutex; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v10; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v11; // [rsp+50h] [rbp-B0h] BYREF
  UCHAR Buffer[208]; // [rsp+60h] [rbp-A0h] BYREF

  v1 = Parameter[1];
  v3 = (unsigned int)dword_14001A2FC;
  FastMutex = 0;
  v11 = 0;
  v10 = 0;
  memset(Buffer, 0, sizeof(Buffer));
  v4 = WimFSFLockSystemBackingVolume((struct _UNICODE_STRING *)(Parameter[2] + 56LL), &FastMutex);
  *((_DWORD *)Parameter + 6) = v4;
  if ( v4 >= 0 )
  {
    v5 = FastMutex;
    WofWakeFromDormant(FastMutex);
    v6 = (char *)v5 + (unsigned int)dword_14001A2FC;
    v7 = WimFSFOpenWimFile(
           *Parameter,
           v1 - v3,
           (__int64)v5,
           (struct _UNICODE_STRING *)(Parameter[2] + 56LL),
           Parameter[2] + 72LL,
           &v11,
           (PFILE_OBJECT *)&v10,
           Buffer);
    *((_DWORD *)Parameter + 6) = v7;
    if ( v7 >= 0 )
    {
      *((_DWORD *)Parameter + 6) = WimFSFAddFileOverlay(
                                     *Parameter,
                                     Parameter[1],
                                     (int)v6,
                                     (unsigned int)Parameter[2] + 72,
                                     Buffer,
                                     v11,
                                     v10,
                                     Parameter[2] + 88LL);
      ExAcquireFastMutexUnsafe(v5);
      if ( *((int *)Parameter + 6) >= 0 && (v8 = Parameter[2], (*(_DWORD *)(v8 + 40) & 8) != 0) )
        *(_QWORD *)(v8 + 32) = v6;
      else
        --*((_DWORD *)v6 + 1);
      ExReleaseFastMutexUnsafe(v5);
      FltReleaseContext(v5);
      if ( *((int *)Parameter + 6) >= 0 )
      {
        if ( ExAcquireRundownProtection(*(PEX_RUNDOWN_REF *)(Parameter[2] + 96LL)) )
        {
          _InterlockedAnd((volatile signed __int32 *)(Parameter[2] + 40LL), 0xFFFFFFFE);
          *((_DWORD *)Parameter + 6) = 0;
        }
        else
        {
          *((_DWORD *)Parameter + 6) = -1073741823;
        }
      }
    }
    else
    {
      ExAcquireFastMutexUnsafe(v5);
      --*((_DWORD *)v6 + 1);
      ExReleaseFastMutexUnsafe(v5);
      FltReleaseContext(v5);
    }
  }
}

```

## disassembly

```asm
0x14002dcc0  push    rbp
0x14002dcc2  push    rbx
0x14002dcc3  push    rsi
0x14002dcc4  push    rdi
0x14002dcc5  push    r14
0x14002dcc7  push    r15
0x14002dcc9  lea     rbp, [rsp-48h]
0x14002dcce  sub     rsp, 148h
0x14002dcd5  mov     rax, cs:__security_cookie
0x14002dcdc  xor     rax, rsp
0x14002dcdf  mov     [rbp+70h+var_40], rax
0x14002dce3  mov     r14, [rcx+8]
0x14002dce7  mov     rbx, rcx
0x14002dcea  mov     r15d, cs:dword_14001A2FC
0x14002dcf1  lea     rcx, [rsp+170h+var_110]; void *
0x14002dcf6  xor     edx, edx; Val
0x14002dcf8  mov     [rsp+170h+FastMutex], 0
0x14002dd01  mov     r8d, 0D0h; Size
0x14002dd07  mov     [rsp+170h+var_120], 0
0x14002dd10  mov     [rsp+170h+var_128], 0
0x14002dd19  call    memset
0x14002dd1e  mov     rcx, [rbx+10h]
0x14002dd22  lea     rdx, [rsp+170h+FastMutex]
0x14002dd27  add     rcx, 38h ; '8'
0x14002dd2b  call    WimFSFLockSystemBackingVolume
0x14002dd30  mov     [rbx+18h], eax
0x14002dd33  test    eax, eax
0x14002dd35  js      loc_14002DE8C
0x14002dd3b  mov     rdi, [rsp+170h+FastMutex]
0x14002dd40  mov     rcx, rdi
0x14002dd43  call    WofWakeFromDormant
0x14002dd48  mov     r9, [rbx+10h]
0x14002dd4c  lea     rcx, [rsp+170h+var_110]
0x14002dd51  mov     esi, cs:dword_14001A2FC
0x14002dd57  sub     r14, r15
0x14002dd5a  mov     [rsp+170h+Buffer], rcx; Buffer
0x14002dd5f  mov     r8, rdi; int
0x14002dd62  lea     rcx, [rsp+170h+var_128]
0x14002dd67  mov     rdx, r14; int
0x14002dd6a  mov     [rsp+170h+var_140], rcx; __int64
0x14002dd6f  lea     rax, [r9+48h]
0x14002dd73  lea     rcx, [rsp+170h+var_120]
0x14002dd78  add     r9, 38h ; '8'; int
0x14002dd7c  mov     [rsp+170h+var_148], rcx; __int64
0x14002dd81  add     rsi, rdi
0x14002dd84  mov     rcx, [rbx]; int
0x14002dd87  mov     [rsp+170h+pbInput], rax; __int64
0x14002dd8c  call    WimFSFOpenWimFile
0x14002dd91  mov     [rbx+18h], eax
0x14002dd94  test    eax, eax
0x14002dd96  jns     short loc_14002DDCD
0x14002dd98  mov     rcx, rdi; FastMutex
0x14002dd9b  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14002dda2  nop     dword ptr [rax+rax+00h]
0x14002dda7  dec     dword ptr [rsi+4]
0x14002ddaa  mov     rcx, rdi; FastMutex
0x14002ddad  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002ddb4  nop     dword ptr [rax+rax+00h]
0x14002ddb9  mov     rcx, rdi; Context
0x14002ddbc  call    cs:__imp_FltReleaseContext
0x14002ddc3  nop     dword ptr [rax+rax+00h]
0x14002ddc8  jmp     loc_14002DE8C
0x14002ddcd  mov     r9, [rbx+10h]
0x14002ddd1  mov     r8, rsi; int
0x14002ddd4  mov     rdx, [rbx+8]; int
0x14002ddd8  mov     rcx, [rbx]; int
0x14002dddb  lea     rax, [r9+58h]
0x14002dddf  add     r9, 48h ; 'H'; int
0x14002dde3  mov     [rsp+170h+Buffer], rax; __int64
0x14002dde8  mov     rax, [rsp+170h+var_128]
0x14002dded  mov     [rsp+170h+var_140], rax; __int64
0x14002ddf2  mov     rax, [rsp+170h+var_120]
0x14002ddf7  mov     [rsp+170h+var_148], rax; __int64
0x14002ddfc  lea     rax, [rsp+170h+var_110]
0x14002de01  mov     [rsp+170h+pbInput], rax; pbInput
0x14002de06  call    WimFSFAddFileOverlay
0x14002de0b  mov     rcx, rdi; FastMutex
0x14002de0e  mov     [rbx+18h], eax
0x14002de11  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14002de18  nop     dword ptr [rax+rax+00h]
0x14002de1d  cmp     dword ptr [rbx+18h], 0
0x14002de21  jl      short loc_14002DE34
0x14002de23  mov     rcx, [rbx+10h]
0x14002de27  mov     eax, [rcx+28h]
0x14002de2a  test    al, 8
0x14002de2c  jz      short loc_14002DE34
0x14002de2e  mov     [rcx+20h], rsi
0x14002de32  jmp     short loc_14002DE37
0x14002de34  dec     dword ptr [rsi+4]
0x14002de37  mov     rcx, rdi; FastMutex
0x14002de3a  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002de41  nop     dword ptr [rax+rax+00h]
0x14002de46  mov     rcx, rdi; Context
0x14002de49  call    cs:__imp_FltReleaseContext
0x14002de50  nop     dword ptr [rax+rax+00h]
0x14002de55  cmp     dword ptr [rbx+18h], 0
0x14002de59  jl      short loc_14002DE8C
0x14002de5b  mov     rcx, [rbx+10h]
0x14002de5f  mov     rcx, [rcx+60h]; RunRef
0x14002de63  call    cs:__imp_ExAcquireRundownProtection
0x14002de6a  nop     dword ptr [rax+rax+00h]
0x14002de6f  test    al, al
0x14002de71  jz      short loc_14002DE85
0x14002de73  mov     rax, [rbx+10h]
0x14002de77  lock and dword ptr [rax+28h], 0FFFFFFFEh
0x14002de7c  mov     dword ptr [rbx+18h], 0
0x14002de83  jmp     short loc_14002DE8C
0x14002de85  mov     dword ptr [rbx+18h], 0C0000001h
0x14002de8c  mov     rcx, [rbp+70h+var_40]
0x14002de90  xor     rcx, rsp; StackCookie
0x14002de93  call    __security_check_cookie
0x14002de98  add     rsp, 148h
0x14002de9f  pop     r15
0x14002dea1  pop     r14
0x14002dea3  pop     rdi
0x14002dea4  pop     rsi
0x14002dea5  pop     rbx
0x14002dea6  pop     rbp
0x14002dea7  retn
```
