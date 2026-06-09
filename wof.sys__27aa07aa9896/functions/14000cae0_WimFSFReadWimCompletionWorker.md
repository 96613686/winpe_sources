# WimFSFReadWimCompletionWorker

- ea: `0x14000cae0`
- end: `0x14000cd37`
- name: `WimFSFReadWimCompletionWorker`
- size: `599`
- prototype: `void __stdcall(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, PVOID Context)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14000afc0`

## callees

- `0x14000a9f0`
- `0x14000cae0`
- `0x14000d3b8`
- `0x14000fb60`
- `0x1400105e8`
- `0x140011640`
- `0x1400116c0`
- `0x140027ffc`

## import_xrefs

- `FLTMGR!FltFreeGenericWorkItem` at `0x14000cce9`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000cce9`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14000cc08`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14000cc08`
- `FLTMGR!FltReleasePushLockEx` at `0x14000cc46`
- `FLTMGR!FltReleasePushLockEx` at `0x14000cc46`

## pseudocode

```c
void __fastcall WimFSFReadWimCompletionWorker(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, _QWORD *Context)
{
  void *v4; // r15
  __int64 v5; // rbp
  __int64 v6; // r14
  __int64 v7; // rbx
  __int64 v8; // r12
  size_t v9; // r13
  const char *v10; // r9
  int v11; // edi
  unsigned int v12; // ebp
  struct _RTL_BITMAP *v13; // rcx
  void (__fastcall *v14)(_QWORD *, PVOID); // rax
  char v16; // [rsp+80h] [rbp+18h]
  unsigned int v17; // [rsp+88h] [rbp+20h]

  v4 = (void *)Context[22];
  v5 = *Context;
  v6 = Context[6];
  v7 = Context[20];
  v8 = Context[21];
  v9 = *((unsigned int *)Context + 39);
  v16 = *((_BYTE *)Context + 152);
  v17 = *((_DWORD *)Context + 46);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids);
  if ( v5 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      v10 = "SYNC";
      if ( !*((_BYTE *)Context + 201) )
        v10 = "ASYNC";
      WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids, v10);
    }
    v11 = *(_DWORD *)(v5 + 24);
    v12 = *(_DWORD *)(v5 + 32);
  }
  else
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids);
    v11 = *((_DWORD *)Context + 2);
    v12 = *((_DWORD *)Context + 58);
  }
  if ( v11 < 0 )
    goto LABEL_26;
  if ( v16 )
  {
    FltAcquirePushLockSharedEx(v6 + 1008, 0);
    v13 = *(struct _RTL_BITMAP **)(v6 + 1016);
    if ( v13 )
    {
      v11 = WimFSFCheckIntegrityOfBlocks(v13, v7, v8, v12);
    }
    else if ( (*(_DWORD *)(v6 + 100) & 0x10) != 0 )
    {
      v11 = *(_DWORD *)(v6 + 1024);
    }
    FltReleasePushLockEx(v6 + 1008, 0);
    if ( v11 < 0 )
      goto LABEL_26;
  }
  if ( v12 < v17 + (unsigned int)v9 )
  {
    v11 = -1073741823;
LABEL_26:
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        47,
        WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids,
        (unsigned int)v11);
    goto LABEL_32;
  }
  if ( (void *)v8 != v4 )
    memmove(v4, (const void *)(v8 + v17), v9);
  v14 = (void (__fastcall *)(_QWORD *, PVOID))Context[30];
  if ( v14 )
  {
    *((_DWORD *)Context + 2) = v11;
    v14(Context, FltObject);
    goto LABEL_33;
  }
LABEL_32:
  WimFSFCompleteRead((char *)Context, v9, v11);
LABEL_33:
  if ( FltWorkItem )
    FltFreeGenericWorkItem(FltWorkItem);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids, (unsigned int)v11);
}

```

## disassembly

```asm
0x14000cae0  mov     [rsp+arg_8], rbx
0x14000cae5  mov     [rsp+FltWorkItem], rcx
0x14000caea  push    rbp
0x14000caeb  push    rsi
0x14000caec  push    rdi
0x14000caed  push    r12
0x14000caef  push    r13
0x14000caf1  push    r14
0x14000caf3  push    r15
0x14000caf5  sub     rsp, 30h
0x14000caf9  mov     al, [r8+98h]
0x14000cb00  mov     rsi, r8
0x14000cb03  mov     r15, [r8+0B0h]
0x14000cb0a  mov     rbp, [r8]
0x14000cb0d  mov     r14, [r8+30h]
0x14000cb11  mov     rbx, [r8+0A0h]
0x14000cb18  mov     r12, [r8+0A8h]
0x14000cb1f  mov     r13d, [r8+9Ch]
0x14000cb26  mov     [rsp+68h+arg_10], al
0x14000cb2d  mov     eax, [r8+0B8h]
0x14000cb34  mov     [rsp+68h+arg_18], eax
0x14000cb3b  mov     [rsp+68h+var_48], r15
0x14000cb40  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cb47  mov     eax, [rcx+2Ch]
0x14000cb4a  test    al, 20h
0x14000cb4c  jz      short loc_14000CB69
0x14000cb4e  cmp     byte ptr [rcx+29h], 4
0x14000cb52  jb      short loc_14000CB69
0x14000cb54  mov     rcx, [rcx+18h]
0x14000cb58  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14000cb5f  mov     edx, 2Ch ; ','
0x14000cb64  call    WPP_SF_
0x14000cb69  test    rbp, rbp
0x14000cb6c  jz      short loc_14000CBB8
0x14000cb6e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cb75  mov     eax, [rcx+2Ch]
0x14000cb78  test    al, 20h
0x14000cb7a  jz      short loc_14000CBB0
0x14000cb7c  cmp     byte ptr [rcx+29h], 5
0x14000cb80  jb      short loc_14000CBB0
0x14000cb82  cmp     byte ptr [rsi+0C9h], 0
0x14000cb89  lea     rdx, aAsync; "ASYNC"
0x14000cb90  mov     rcx, [rcx+18h]
0x14000cb94  lea     r9, aSync; "SYNC"
0x14000cb9b  cmovz   r9, rdx
0x14000cb9f  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14000cba6  mov     edx, 2Dh ; '-'
0x14000cbab  call    WPP_SF_s
0x14000cbb0  mov     edi, [rbp+18h]
0x14000cbb3  mov     ebp, [rbp+20h]
0x14000cbb6  jmp     short loc_14000CBEA
0x14000cbb8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cbbf  mov     eax, [rcx+2Ch]
0x14000cbc2  test    al, 20h
0x14000cbc4  jz      short loc_14000CBE1
0x14000cbc6  cmp     byte ptr [rcx+29h], 5
0x14000cbca  jb      short loc_14000CBE1
0x14000cbcc  mov     rcx, [rcx+18h]
0x14000cbd0  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14000cbd7  mov     edx, 2Eh ; '.'
0x14000cbdc  call    WPP_SF_
0x14000cbe1  mov     edi, [rsi+8]
0x14000cbe4  mov     ebp, [rsi+0E8h]
0x14000cbea  test    edi, edi
0x14000cbec  js      loc_14000CC85
0x14000cbf2  cmp     [rsp+68h+arg_10], 0
0x14000cbfa  jz      short loc_14000CC5B
0x14000cbfc  lea     r15, [r14+3F0h]
0x14000cc03  xor     edx, edx
0x14000cc05  mov     rcx, r15
0x14000cc08  call    cs:__imp_FltAcquirePushLockSharedEx
0x14000cc0f  nop     dword ptr [rax+rax+00h]
0x14000cc14  mov     rcx, [r14+3F8h]; BitMapHeader
0x14000cc1b  test    rcx, rcx
0x14000cc1e  jz      short loc_14000CC32
0x14000cc20  mov     r9d, ebp
0x14000cc23  mov     r8, r12
0x14000cc26  mov     rdx, rbx
0x14000cc29  call    WimFSFCheckIntegrityOfBlocks
0x14000cc2e  mov     edi, eax
0x14000cc30  jmp     short loc_14000CC41
0x14000cc32  mov     eax, [r14+64h]
0x14000cc36  test    al, 10h
0x14000cc38  jz      short loc_14000CC41
0x14000cc3a  mov     edi, [r14+400h]
0x14000cc41  xor     edx, edx
0x14000cc43  mov     rcx, r15
0x14000cc46  call    cs:__imp_FltReleasePushLockEx
0x14000cc4d  nop     dword ptr [rax+rax+00h]
0x14000cc52  test    edi, edi
0x14000cc54  js      short loc_14000CC85
0x14000cc56  mov     r15, [rsp+68h+var_48]
0x14000cc5b  mov     ecx, [rsp+68h+arg_18]
0x14000cc62  lea     eax, [rcx+r13]
0x14000cc66  cmp     ebp, eax
0x14000cc68  jb      short loc_14000CC80
0x14000cc6a  cmp     r12, r15
0x14000cc6d  jz      short loc_14000CCB5
0x14000cc6f  lea     rdx, [r12+rcx]; Src
0x14000cc73  mov     r8, r13; Size
0x14000cc76  mov     rcx, r15; void *
0x14000cc79  call    memmove
0x14000cc7e  jmp     short loc_14000CCB5
0x14000cc80  mov     edi, 0C0000001h
0x14000cc85  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cc8c  mov     eax, [rcx+2Ch]
0x14000cc8f  test    al, 20h
0x14000cc91  jz      short loc_14000CCB1
0x14000cc93  cmp     byte ptr [rcx+29h], 2
0x14000cc97  jb      short loc_14000CCB1
0x14000cc99  mov     rcx, [rcx+18h]
0x14000cc9d  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14000cca4  mov     edx, 2Fh ; '/'
0x14000cca9  mov     r9d, edi
0x14000ccac  call    WPP_SF_d
0x14000ccb1  test    edi, edi
0x14000ccb3  js      short loc_14000CCCE
0x14000ccb5  mov     rax, [rsi+0F0h]
0x14000ccbc  test    rax, rax
0x14000ccbf  jz      short loc_14000CCCE
0x14000ccc1  mov     rcx, rsi
0x14000ccc4  mov     [rsi+8], edi
0x14000ccc7  call    _guard_dispatch_icall
0x14000cccc  jmp     short loc_14000CCDC
0x14000ccce  mov     r8d, edi
0x14000ccd1  mov     edx, r13d
0x14000ccd4  mov     rcx, rsi; Entry
0x14000ccd7  call    WimFSFCompleteRead
0x14000ccdc  mov     rax, [rsp+68h+FltWorkItem]
0x14000cce1  test    rax, rax
0x14000cce4  jz      short loc_14000CCF5
0x14000cce6  mov     rcx, rax; FltWorkItem
0x14000cce9  call    cs:__imp_FltFreeGenericWorkItem
0x14000ccf0  nop     dword ptr [rax+rax+00h]
0x14000ccf5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ccfc  mov     eax, [rcx+2Ch]
0x14000ccff  test    al, 20h
0x14000cd01  jz      short loc_14000CD21
0x14000cd03  cmp     byte ptr [rcx+29h], 4
0x14000cd07  jb      short loc_14000CD21
0x14000cd09  mov     rcx, [rcx+18h]
0x14000cd0d  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14000cd14  mov     edx, 30h ; '0'
0x14000cd19  mov     r9d, edi
0x14000cd1c  call    WPP_SF_d
0x14000cd21  mov     rbx, [rsp+68h+arg_8]
0x14000cd26  add     rsp, 30h
0x14000cd2a  pop     r15
0x14000cd2c  pop     r14
0x14000cd2e  pop     r13
0x14000cd30  pop     r12
0x14000cd32  pop     rdi
0x14000cd33  pop     rsi
0x14000cd34  pop     rbp
0x14000cd35  retn
```
