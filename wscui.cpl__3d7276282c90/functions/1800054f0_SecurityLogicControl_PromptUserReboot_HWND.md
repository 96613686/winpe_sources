# SecurityLogicControl::PromptUserReboot(HWND__ *)

- ea: `0x1800054f0`
- end: `0x1800055aa`
- name: `?PromptUserReboot@SecurityLogicControl@@SAHPEAUHWND__@@@Z`
- size: `186`
- prototype: `__int64 __fastcall(HWND)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006520`

## callees

- `0x1800054f0`
- `0x180006340`
- `0x18000a616`

## pseudocode

```c
_BOOL8 __fastcall SecurityLogicControl::PromptUserReboot(HWND a1)
{
  __int64 v2; // r8
  int v4; // [rsp+20h] [rbp-69h] BYREF
  __int64 v5; // [rsp+24h] [rbp-65h]
  int v6; // [rsp+2Ch] [rbp-5Dh]
  __int64 v7; // [rsp+30h] [rbp-59h]
  int v8; // [rsp+40h] [rbp-49h] BYREF
  _QWORD v9[7]; // [rsp+44h] [rbp-45h] BYREF
  int v10; // [rsp+7Ch] [rbp-Dh]
  int *v11; // [rsp+80h] [rbp-9h]
  int v12; // [rsp+F0h] [rbp+67h] BYREF

  v12 = 0;
  v4 = 1;
  v5 = 1129;
  v6 = 2;
  v7 = 1130;
  v8 = 160;
  memset_0(v9, 0, 0x9Cu);
  v9[1] = hInstance;
  v9[0] = a1;
  v11 = &v4;
  v9[3] = 1180;
  v9[5] = 1050;
  v9[4] = 65531;
  v10 = 2;
  return (int)IsolationAwareTaskDialogIndirect((__int64)&v8, (__int64)&v12, v2, 0) >= 0 && v12 == 1;
}

```

## disassembly

```asm
0x1800054f0  mov     [rsp-8+arg_8], rbx
0x1800054f5  push    rbp
0x1800054f6  lea     rbp, [rsp-57h]
0x1800054fb  sub     rsp, 0E0h
0x180005502  mov     rbx, rcx
0x180005505  mov     [rbp+57h+arg_0], 0
0x18000550c  lea     rcx, [rbp+57h+var_9C]; void *
0x180005510  mov     [rbp+57h+var_C0], 1
0x180005517  xor     edx, edx; Val
0x180005519  mov     [rbp+57h+var_BC], 469h
0x180005521  mov     r8d, 9Ch; Size
0x180005527  mov     [rbp+57h+var_B4], 2
0x18000552e  mov     [rbp+57h+var_B0], 46Ah
0x180005536  mov     [rbp+57h+var_A0], 0A0h
0x18000553d  call    memset_0
0x180005542  mov     rax, cs:hInstance
0x180005549  lea     rdx, [rbp+57h+arg_0]
0x18000554d  mov     [rbp+57h+var_94], rax
0x180005551  lea     rcx, [rbp+57h+var_A0]
0x180005555  lea     rax, [rbp+57h+var_C0]
0x180005559  mov     [rbp+57h+var_9C], rbx
0x18000555d  xor     r9d, r9d
0x180005560  mov     [rbp+57h+var_60], rax
0x180005564  mov     [rbp+57h+var_84], 49Ch
0x18000556c  mov     [rbp+57h+var_74], 41Ah
0x180005574  mov     [rbp+57h+var_7C], 0FFFBh
0x18000557c  mov     [rbp+57h+var_64], 2
0x180005583  call    IsolationAwareTaskDialogIndirect
0x180005588  test    eax, eax
0x18000558a  js      short loc_180005597
0x18000558c  xor     eax, eax
0x18000558e  cmp     [rbp+57h+arg_0], 1
0x180005592  setz    al
0x180005595  jmp     short loc_180005599
0x180005597  xor     eax, eax
0x180005599  mov     rbx, [rsp+0E0h+arg_8]
0x1800055a1  add     rsp, 0E0h
0x1800055a8  pop     rbp
0x1800055a9  retn
```
