# LBS_CALL::ChangeCallState(_CallStates,long)

- ea: `0x18001f9f4`
- end: `0x18001fac2`
- name: `?ChangeCallState@LBS_CALL@@QEAAXW4_CallStates@@J@Z`
- size: `206`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x18001f898`
- `0x18001fac8`
- `0x180020c3c`
- `0x1800214a4`
- `0x180021544`
- `0x1800215e4`
- `0x180021698`
- `0x180021744`
- `0x18002199c`

## callees

- `0x18001b930`
- `0x18001f9f4`

## import_xrefs

- `RPCRT4!I_RpcLogEvent` at `0x18001fa3c`
- `RPCRT4!I_RpcLogEvent` at `0x18001fa3c`

## pseudocode

```c
__int64 __fastcall LBS_CALL::ChangeCallState(__int64 a1, __int64 a2, int a3)
{
  ULONG_PTR v3; // rbx
  __int64 v4; // rdi
  int v5; // r9d
  __int64 result; // rax
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  bool v12; // zf
  bool v13; // cc

  v3 = (int)a2;
  v4 = a1;
  if ( (_DWORD)a2 == 6 )
    *(_DWORD *)(a1 + 156) = a3;
  v5 = *(_DWORD *)(a1 + 148);
  LOBYTE(a2) = 61;
  LOBYTE(a1) = 67;
  result = I_RpcLogEvent(a1, a2, v4, (unsigned int)v3 | (unsigned __int64)(unsigned int)(v5 << 16), a3, 1, 0);
  v7 = *(_DWORD *)(v4 + 148);
  if ( !v7 )
  {
    result = (unsigned int)(v3 - 1);
    if ( (result & 0xFFFFFFFA) == 0 && (_DWORD)v3 != 5 )
      goto LABEL_20;
LABEL_13:
    RpcpReportFatalError(*(int *)(v4 + 148), v3);
    __debugbreak();
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    result = (unsigned int)(v3 - 2);
    v13 = (unsigned int)result <= 4;
LABEL_16:
    if ( v13 )
      goto LABEL_20;
    goto LABEL_13;
  }
  v9 = v8 - 1;
  if ( !v9 )
    goto LABEL_14;
  v10 = v9 - 1;
  if ( !v10 )
  {
    result = (unsigned int)(v3 - 2);
    v12 = (result & 0xFFFFFFFB) == 0;
    goto LABEL_12;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
LABEL_14:
    result = (unsigned int)(v3 - 5);
    v13 = (unsigned int)result <= 1;
    goto LABEL_16;
  }
  if ( v11 != 1 )
  {
    RpcpReportFatalError(*(int *)(v4 + 148), 0);
    __debugbreak();
  }
  v12 = (_DWORD)v3 == 6;
LABEL_12:
  if ( !v12 )
    goto LABEL_13;
LABEL_20:
  *(_DWORD *)(v4 + 148) = v3;
  return result;
}

```

## disassembly

```asm
0x18001f9f4  mov     [rsp+arg_0], rbx
0x18001f9f9  push    rdi
0x18001f9fa  sub     rsp, 40h
0x18001f9fe  movsxd  rbx, edx
0x18001fa01  mov     rdi, rcx
0x18001fa04  cmp     ebx, 6
0x18001fa07  jnz     short loc_18001FA10
0x18001fa09  mov     [rcx+9Ch], r8d
0x18001fa10  mov     r9d, [rcx+94h]
0x18001fa17  mov     dl, 3Dh ; '='
0x18001fa19  mov     [rsp+48h+var_18], 0
0x18001fa21  mov     cl, 43h ; 'C'
0x18001fa23  shl     r9d, 10h
0x18001fa27  mov     eax, ebx
0x18001fa29  mov     [rsp+48h+var_20], 1
0x18001fa31  or      r9, rax
0x18001fa34  mov     [rsp+48h+var_28], r8d
0x18001fa39  mov     r8, rdi
0x18001fa3c  call    cs:__imp_I_RpcLogEvent
0x18001fa42  movsxd  r8, dword ptr [rdi+94h]
0x18001fa49  mov     ecx, r8d
0x18001fa4c  test    r8d, r8d
0x18001fa4f  jz      short loc_18001FAA2
0x18001fa51  sub     ecx, 1
0x18001fa54  jz      short loc_18001FA98
0x18001fa56  sub     ecx, 1
0x18001fa59  jz      short loc_18001FA90
0x18001fa5b  sub     ecx, 1
0x18001fa5e  jz      short loc_18001FA7A
0x18001fa60  sub     ecx, 1
0x18001fa63  jz      short loc_18001FA90
0x18001fa65  cmp     ecx, 1
0x18001fa68  jz      short loc_18001FA75
0x18001fa6a  mov     rcx, r8
0x18001fa6d  xor     edx, edx
0x18001fa6f  call    RpcpReportFatalError
0x18001fa74  int     3; Trap to Debugger
0x18001fa75  cmp     ebx, 6
0x18001fa78  jmp     short loc_18001FA82
0x18001fa7a  lea     eax, [rbx-2]
0x18001fa7d  test    eax, 0FFFFFFFBh
0x18001fa82  jz      short loc_18001FAB1
0x18001fa84  mov     rdx, rbx
0x18001fa87  mov     rcx, r8
0x18001fa8a  call    RpcpReportFatalError
0x18001fa8f  int     3; Trap to Debugger
0x18001fa90  lea     eax, [rbx-5]
0x18001fa93  cmp     eax, 1
0x18001fa96  jmp     short loc_18001FA9E
0x18001fa98  lea     eax, [rbx-2]
0x18001fa9b  cmp     eax, 4
0x18001fa9e  ja      short loc_18001FA84
0x18001faa0  jmp     short loc_18001FAB1
0x18001faa2  lea     eax, [rbx-1]
0x18001faa5  test    eax, 0FFFFFFFAh
0x18001faaa  jnz     short loc_18001FA84
0x18001faac  cmp     ebx, 5
0x18001faaf  jz      short loc_18001FA84
0x18001fab1  mov     [rdi+94h], ebx
0x18001fab7  mov     rbx, [rsp+48h+arg_0]
0x18001fabc  add     rsp, 40h
0x18001fac0  pop     rdi
0x18001fac1  retn
```
