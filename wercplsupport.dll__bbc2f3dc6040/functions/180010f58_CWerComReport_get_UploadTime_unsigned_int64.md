# CWerComReport::_get_UploadTime(unsigned __int64 *)

- ea: `0x180010f58`
- end: `0x180011032`
- name: `?_get_UploadTime@CWerComReport@@QEAAJPEA_K@Z`
- size: `218`
- prototype: `__int64 __fastcall(CWerComReport *__hidden this, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011bc0`

## callees

- `0x180006c9c`
- `0x18000e35c`
- `0x180010f58`

## import_xrefs

- `wer!WerpGetUploadTime` at `0x180010fdd`
- `wer!WerpGetUploadTime` at `0x180010fdd`

## pseudocode

```c
__int64 __fastcall CWerComReport::_get_UploadTime(CWerComReport *this, unsigned __int64 *a2)
{
  int WerApiLock; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v8; // [rsp+40h] [rbp+18h] BYREF
  unsigned __int64 v9; // [rsp+48h] [rbp+20h] BYREF

  v9 = 0;
  v8 = 0;
  WerApiLock = CWerApiAutoLock::TryGetWerApiLock((CWerApiAutoLock *)&v8, this);
  if ( WerApiLock < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 41;
LABEL_5:
      WPP_SF_d(v5[2], v6, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids, (unsigned int)WerApiLock);
      goto LABEL_6;
    }
    goto LABEL_6;
  }
  WerApiLock = WerpGetUploadTime(*((_QWORD *)this + 4), &v9);
  if ( WerApiLock < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 42;
      goto LABEL_5;
    }
LABEL_6:
    if ( v8 )
      _InterlockedExchange((volatile __int32 *)(v8 + 48), 0);
    return (unsigned int)WerApiLock;
  }
  *a2 = v9;
  if ( v8 )
    _InterlockedExchange((volatile __int32 *)(v8 + 48), 0);
  return 0;
}

```

## disassembly

```asm
0x180010f58  mov     rax, rsp
0x180010f5b  mov     [rax+8], rbx
0x180010f5f  mov     [rax+10h], rsi
0x180010f63  push    rdi
0x180010f64  sub     rsp, 20h
0x180010f68  mov     rsi, rdx
0x180010f6b  mov     qword ptr [rax+20h], 0
0x180010f73  mov     rdx, rcx; struct CWerComReport *
0x180010f76  mov     qword ptr [rax+18h], 0
0x180010f7e  mov     rdi, rcx
0x180010f81  lea     rcx, [rax+18h]; this
0x180010f85  call    ?TryGetWerApiLock@CWerApiAutoLock@@QEAAJPEAVCWerComReport@@@Z; CWerApiAutoLock::TryGetWerApiLock(CWerComReport *)
0x180010f8a  mov     ebx, eax
0x180010f8c  test    eax, eax
0x180010f8e  jns     short loc_180010FD4
0x180010f90  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f97  lea     rdx, WPP_GLOBAL_Control
0x180010f9e  cmp     rcx, rdx
0x180010fa1  jz      short loc_180010FC1
0x180010fa3  test    byte ptr [rcx+1Ch], 1
0x180010fa7  jz      short loc_180010FC1
0x180010fa9  mov     edx, 29h ; ')'
0x180010fae  mov     rcx, [rcx+10h]
0x180010fb2  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x180010fb9  mov     r9d, ebx
0x180010fbc  call    WPP_SF_d
0x180010fc1  mov     rax, [rsp+28h+arg_10]
0x180010fc6  test    rax, rax
0x180010fc9  jz      short loc_180010FD0
0x180010fcb  xor     ecx, ecx
0x180010fcd  xchg    ecx, [rax+30h]
0x180010fd0  mov     eax, ebx
0x180010fd2  jmp     short loc_180011022
0x180010fd4  mov     rcx, [rdi+20h]
0x180010fd8  lea     rdx, [rsp+28h+arg_18]
0x180010fdd  call    cs:__imp_WerpGetUploadTime
0x180010fe3  mov     ebx, eax
0x180010fe5  test    eax, eax
0x180010fe7  jns     short loc_180011009
0x180010fe9  mov     rcx, cs:WPP_GLOBAL_Control
0x180010ff0  lea     rdx, WPP_GLOBAL_Control
0x180010ff7  cmp     rcx, rdx
0x180010ffa  jz      short loc_180010FC1
0x180010ffc  test    byte ptr [rcx+1Ch], 1
0x180011000  jz      short loc_180010FC1
0x180011002  mov     edx, 2Ah ; '*'
0x180011007  jmp     short loc_180010FAE
0x180011009  mov     rax, [rsp+28h+arg_18]
0x18001100e  mov     [rsi], rax
0x180011011  mov     rax, [rsp+28h+arg_10]
0x180011016  test    rax, rax
0x180011019  jz      short loc_180011020
0x18001101b  xor     ecx, ecx
0x18001101d  xchg    ecx, [rax+30h]
0x180011020  xor     eax, eax
0x180011022  mov     rbx, [rsp+28h+arg_0]
0x180011027  mov     rsi, [rsp+28h+arg_8]
0x18001102c  add     rsp, 20h
0x180011030  pop     rdi
0x180011031  retn
```
