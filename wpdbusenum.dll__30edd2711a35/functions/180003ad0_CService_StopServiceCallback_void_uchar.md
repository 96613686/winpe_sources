# CService::StopServiceCallback(void *,uchar)

- ea: `0x180003ad0`
- end: `0x180003b57`
- name: `?StopServiceCallback@CService@@KAXPEAXE@Z`
- size: `135`
- prototype: `void __fastcall(CService *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180003ad0`
- `0x180003b60`
- `0x180007f28`
- `0x18000ea08`

## pseudocode

```c
void __fastcall CService::StopServiceCallback(CService *a1, unsigned int a2)
{
  int v2; // eax

  if ( a1 )
  {
    v2 = CService::Stop(a1, a2);
    if ( v2 < 0
      && WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        70,
        &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids,
        (unsigned int)v2);
    }
  }
  else if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids, 0, -2147418113);
  }
}

```

## disassembly

```asm
0x180003ad0  sub     rsp, 38h
0x180003ad4  test    rcx, rcx
0x180003ad7  jnz     short loc_180003B14
0x180003ad9  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ae0  lea     rdx, WPP_GLOBAL_Control
0x180003ae7  cmp     rcx, rdx
0x180003aea  jz      short loc_180003B52
0x180003aec  test    byte ptr [rcx+1Ch], 2
0x180003af0  jz      short loc_180003B52
0x180003af2  mov     rcx, [rcx+10h]
0x180003af6  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180003afd  mov     edx, 45h ; 'E'
0x180003b02  mov     [rsp+38h+var_18], 8000FFFFh
0x180003b0a  xor     r9d, r9d
0x180003b0d  call    WPP_SF_qd
0x180003b12  jmp     short loc_180003B52
0x180003b14  call    ?Stop@CService@@QEAAJXZ; CService::Stop(void)
0x180003b19  test    eax, eax
0x180003b1b  jns     short loc_180003B52
0x180003b1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b24  lea     rdx, WPP_GLOBAL_Control
0x180003b2b  cmp     rcx, rdx
0x180003b2e  jz      short loc_180003B52
0x180003b30  test    byte ptr [rcx+1Ch], 2
0x180003b34  jz      short loc_180003B52
0x180003b36  mov     rcx, [rcx+10h]
0x180003b3a  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180003b41  mov     edx, 46h ; 'F'
0x180003b46  mov     r9d, eax
0x180003b49  add     rsp, 38h
0x180003b4d  jmp     WPP_SF_d
0x180003b52  add     rsp, 38h
0x180003b56  retn
```
