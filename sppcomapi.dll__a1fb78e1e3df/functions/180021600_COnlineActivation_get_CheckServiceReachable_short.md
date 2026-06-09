# COnlineActivation::get_CheckServiceReachable(short *)

- ea: `0x180021600`
- end: `0x180021662`
- name: `?get_CheckServiceReachable@COnlineActivation@@UEAAJPEAF@Z`
- size: `98`
- prototype: `__int64 __fastcall(COnlineActivation *__hidden this, __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180003520`
- `0x180004288`
- `0x180021600`
- `0x180022f1c`

## pseudocode

```c
__int64 __fastcall COnlineActivation::get_CheckServiceReachable(COnlineActivation *this, __int16 *a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rcx
  int v5; // eax
  __int16 v6; // ax
  int v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = 0;
  if ( !a2 )
  {
    v3 = -2147024809;
    v4 = 2147942487LL;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
    goto LABEL_10;
  }
  v5 = SPPGetServersReachable(&v8);
  v3 = v5;
  if ( v5 < 0 )
  {
    v4 = (unsigned int)v5;
    goto LABEL_3;
  }
  if ( v8 )
    v6 = -1;
  else
    v6 = 0;
  *a2 = v6;
LABEL_10:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  return v3;
}

```

## disassembly

```asm
0x180021600  mov     [rsp+arg_0], rbx
0x180021605  push    rdi
0x180021606  sub     rsp, 20h
0x18002160a  mov     [rsp+28h+arg_8], 0
0x180021612  mov     rdi, rdx
0x180021615  test    rdx, rdx
0x180021618  jnz     short loc_180021628
0x18002161a  mov     ebx, 80070057h
0x18002161f  mov     ecx, ebx
0x180021621  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180021626  jmp     short loc_18002164D
0x180021628  lea     rcx, [rsp+28h+arg_8]; int *
0x18002162d  call    ?SPPGetServersReachable@@YAJPEAH@Z; SPPGetServersReachable(int *)
0x180021632  mov     ebx, eax
0x180021634  test    eax, eax
0x180021636  jns     short loc_18002163C
0x180021638  mov     ecx, eax
0x18002163a  jmp     short loc_180021621
0x18002163c  cmp     [rsp+28h+arg_8], 0
0x180021641  jz      short loc_180021648
0x180021643  or      eax, 0FFFFFFFFh
0x180021646  jmp     short loc_18002164A
0x180021648  xor     eax, eax
0x18002164a  mov     [rdi], ax
0x18002164d  mov     ecx, ebx
0x18002164f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180021654  mov     eax, ebx
0x180021656  mov     rbx, [rsp+28h+arg_0]
0x18002165b  add     rsp, 20h
0x18002165f  pop     rdi
0x180021660  retn
```
