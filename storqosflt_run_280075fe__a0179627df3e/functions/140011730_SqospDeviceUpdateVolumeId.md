# SqospDeviceUpdateVolumeId

- ea: `0x140011730`
- end: `0x1400117de`
- name: `SqospDeviceUpdateVolumeId`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14001223c`

## callees

- `0x140008d20`
- `0x140011730`
- `0x140011b00`

## import_xrefs

- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140011780`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140011780`
- `FLTMGR!FltReleasePushLockEx` at `0x1400117af`
- `FLTMGR!FltReleasePushLockEx` at `0x1400117af`

## pseudocode

```c
char __fastcall SqospDeviceUpdateVolumeId(__int64 a1, _OWORD *a2)
{
  char result; // al

  if ( *(_BYTE *)(a1 + 929) )
  {
    if ( (int)SqospQueryVolumeId(*(PFLT_VOLUME *)a1) < 0 )
      return 0;
    FltAcquirePushLockExclusiveEx(&SqosGlobals, 0);
    if ( *(_BYTE *)(a1 + 929) )
    {
      *(_BYTE *)(a1 + 929) = 0;
      *(_OWORD *)(a1 + 8) = 0;
    }
    FltReleasePushLockEx(&SqosGlobals, 0);
  }
  result = 1;
  *a2 = *(_OWORD *)(a1 + 8);
  return result;
}

```

## disassembly

```asm
0x140011730  mov     [rsp+arg_10], rbx
0x140011735  push    rdi
0x140011736  sub     rsp, 40h
0x14001173a  mov     rax, cs:__security_cookie
0x140011741  xor     rax, rsp
0x140011744  mov     [rsp+48h+var_18], rax
0x140011749  cmp     byte ptr [rcx+3A1h], 0
0x140011750  xorps   xmm0, xmm0
0x140011753  movups  [rsp+48h+var_28], xmm0
0x140011758  mov     rdi, rdx
0x14001175b  mov     rbx, rcx
0x14001175e  jz      short loc_1400117BB
0x140011760  mov     rcx, [rcx]; Volume
0x140011763  lea     r8, [rsp+48h+var_28]
0x140011768  xor     edx, edx
0x14001176a  call    SqospQueryVolumeId
0x14001176f  test    eax, eax
0x140011771  jns     short loc_140011777
0x140011773  xor     al, al
0x140011775  jmp     short loc_1400117C5
0x140011777  xor     edx, edx
0x140011779  lea     rcx, SqosGlobals
0x140011780  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140011787  nop     dword ptr [rax+rax+00h]
0x14001178c  cmp     byte ptr [rbx+3A1h], 0
0x140011793  jz      short loc_1400117A6
0x140011795  movups  xmm0, [rsp+48h+var_28]
0x14001179a  mov     byte ptr [rbx+3A1h], 0
0x1400117a1  movdqu  xmmword ptr [rbx+8], xmm0
0x1400117a6  xor     edx, edx
0x1400117a8  lea     rcx, SqosGlobals
0x1400117af  call    cs:__imp_FltReleasePushLockEx
0x1400117b6  nop     dword ptr [rax+rax+00h]
0x1400117bb  movups  xmm0, xmmword ptr [rbx+8]
0x1400117bf  mov     al, 1
0x1400117c1  movdqu  xmmword ptr [rdi], xmm0
0x1400117c5  mov     rcx, [rsp+48h+var_18]
0x1400117ca  xor     rcx, rsp; StackCookie
0x1400117cd  call    __security_check_cookie
0x1400117d2  mov     rbx, [rsp+48h+arg_10]
0x1400117d7  add     rsp, 40h
0x1400117db  pop     rdi
0x1400117dc  retn
```
