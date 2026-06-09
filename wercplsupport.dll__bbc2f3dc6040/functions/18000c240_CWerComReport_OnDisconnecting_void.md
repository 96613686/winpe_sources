# CWerComReport::OnDisconnecting(void)

- ea: `0x18000c240`
- end: `0x18000c28a`
- name: `?OnDisconnecting@CWerComReport@@UEAAXXZ`
- size: `74`
- prototype: `void __fastcall(CWerComReport *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002850`
- `0x18000c240`

## import_xrefs

- `wer!WerpCancelUpload` at `0x18000c24d`
- `wer!WerpCancelUpload` at `0x18000c24d`

## pseudocode

```c
void __fastcall CWerComReport::OnDisconnecting(CWerComReport *this)
{
  __int64 v1; // rcx

  v1 = *((_QWORD *)this + 4);
  if ( v1
    && (int)WerpCancelUpload(v1) < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
  }
}

```

## disassembly

```asm
0x18000c240  sub     rsp, 28h
0x18000c244  mov     rcx, [rcx+20h]
0x18000c248  test    rcx, rcx
0x18000c24b  jz      short loc_18000C285
0x18000c24d  call    cs:__imp_WerpCancelUpload
0x18000c253  test    eax, eax
0x18000c255  jns     short loc_18000C285
0x18000c257  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c25e  lea     rax, WPP_GLOBAL_Control
0x18000c265  cmp     rcx, rax
0x18000c268  jz      short loc_18000C285
0x18000c26a  test    byte ptr [rcx+1Ch], 1
0x18000c26e  jz      short loc_18000C285
0x18000c270  mov     rcx, [rcx+10h]
0x18000c274  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000c27b  mov     edx, 52h ; 'R'
0x18000c280  call    WPP_SF_
0x18000c285  add     rsp, 28h
0x18000c289  retn
```
