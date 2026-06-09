# DeviceIdNeedsInstall

- ea: `0x180009890`
- end: `0x1800099c3`
- name: `DeviceIdNeedsInstall`
- size: `307`
- prototype: `__int64 __fastcall(DEVINSTID_W pDeviceID, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180009d70`

## callees

- `0x180009890`
- `0x180009a20`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x1800098cb`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x1800098cb`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Status` at `0x1800098f1`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Status` at `0x1800098f1`

## pseudocode

```c
__int64 __fastcall DeviceIdNeedsInstall(DEVINSTID_W pDeviceID, int *a2)
{
  int v4; // edi
  unsigned int v5; // ebx
  __int16 v6; // ax
  __int64 result; // rax
  DEVNODE v8; // [rsp+28h] [rbp-40h]
  ULONG v9[4]; // [rsp+30h] [rbp-38h] BYREF
  ULONG pulProblemNumber; // [rsp+78h] [rbp+10h] BYREF
  DEVINST dnDevInst; // [rsp+80h] [rbp+18h] BYREF
  ULONG pulStatus; // [rsp+88h] [rbp+20h] BYREF

  pulStatus = 0;
  pulProblemNumber = 0;
  dnDevInst = 0;
  v4 = 0;
  if ( CM_Locate_DevNodeW(&dnDevInst, pDeviceID, 5u)
    || CM_Get_DevNode_Status(&pulStatus, &pulProblemNumber, dnDevInst, 0)
    || (pulStatus & 0x40000) != 0
    || (pulStatus & 0x400) != 0 && pulProblemNumber == 22 )
  {
    v5 = 0;
    goto LABEL_11;
  }
  v5 = 1;
  if ( (pulStatus & 0x400) == 0 )
    goto LABEL_6;
  if ( pulProblemNumber == 18 )
  {
    v4 = 1;
    goto LABEL_11;
  }
  if ( pulProblemNumber == 1 )
  {
    v4 = 2;
  }
  else
  {
LABEL_6:
    dnDevInst = 0;
    v9[0] = 4;
    v9[1] = 0;
    if ( (unsigned int)PnpGetDeviceRegProp(pDeviceID, v9, v8) )
      v6 = 0;
    else
      v6 = dnDevInst;
    if ( (v6 & 0x20) != 0 )
    {
      v4 = 3;
    }
    else if ( (v6 & 0x400) != 0 )
    {
      v4 = 4;
    }
  }
LABEL_11:
  result = v5;
  if ( a2 )
    *a2 = v4;
  return result;
}

```

## disassembly

```asm
0x180009890  mov     rax, rsp
0x180009893  push    rbx
0x180009894  push    rsi
0x180009895  push    rdi
0x180009896  sub     rsp, 50h
0x18000989a  mov     [rax+8], rbp
0x18000989e  mov     rsi, rdx
0x1800098a1  mov     [rax-20h], r14
0x1800098a5  mov     rbp, rcx
0x1800098a8  xor     r14d, r14d
0x1800098ab  mov     [rax-28h], r15
0x1800098af  mov     rdx, rcx; pDeviceID
0x1800098b2  mov     [rax+20h], r14d
0x1800098b6  mov     r8d, 5; ulFlags
0x1800098bc  mov     [rax+10h], r14d
0x1800098c0  lea     rcx, [rax+18h]; pdnDevInst
0x1800098c4  mov     [rax+18h], r14d
0x1800098c8  mov     edi, r14d
0x1800098cb  call    cs:__imp_CM_Locate_DevNodeW
0x1800098d1  test    eax, eax
0x1800098d3  jnz     loc_180009986
0x1800098d9  mov     r8d, [rsp+68h+dnDevInst]; dnDevInst
0x1800098e1  lea     rdx, [rsp+68h+pulProblemNumber]; pulProblemNumber
0x1800098e6  xor     r9d, r9d; ulFlags
0x1800098e9  lea     rcx, [rsp+68h+pulStatus]; pulStatus
0x1800098f1  call    cs:__imp_CM_Get_DevNode_Status
0x1800098f7  test    eax, eax
0x1800098f9  jnz     loc_180009986
0x1800098ff  mov     eax, [rsp+68h+pulStatus]
0x180009906  bt      eax, 12h
0x18000990a  jb      short loc_180009986
0x18000990c  and     eax, 400h
0x180009911  jnz     short loc_18000998B
0x180009913  mov     ebx, 1
0x180009918  test    eax, eax
0x18000991a  jnz     short loc_180009997
0x18000991c  lea     rax, [rsp+68h+var_38]
0x180009921  mov     [rsp+68h+dnDevInst], r14d
0x180009929  mov     r15d, 4
0x18000992f  mov     [rsp+68h+var_48], rax; PULONG
0x180009934  lea     r9, [rsp+68h+dnDevInst]
0x18000993c  mov     [rsp+68h+var_38], r15d
0x180009941  lea     r8, [rsp+68h+var_34]
0x180009946  mov     [rsp+68h+var_34], r14d
0x18000994b  mov     rcx, rbp; pDeviceID
0x18000994e  call    PnpGetDeviceRegProp
0x180009953  test    eax, eax
0x180009955  jz      short loc_1800099B3
0x180009957  mov     eax, r14d
0x18000995a  test    al, 20h
0x18000995c  jnz     short loc_1800099BC
0x18000995e  bt      eax, 0Ah
0x180009962  cmovb   edi, r15d
0x180009966  mov     r15, [rsp+68h+var_28]
0x18000996b  mov     eax, ebx
0x18000996d  mov     r14, [rsp+68h+var_20]
0x180009972  mov     rbp, [rsp+68h+arg_0]
0x180009977  test    rsi, rsi
0x18000997a  jz      short loc_18000997E
0x18000997c  mov     [rsi], edi
0x18000997e  add     rsp, 50h
0x180009982  pop     rdi
0x180009983  pop     rsi
0x180009984  pop     rbx
0x180009985  retn
0x180009986  mov     ebx, r14d
0x180009989  jmp     short loc_180009966
0x18000998b  cmp     [rsp+68h+pulProblemNumber], 16h
0x180009990  jz      short loc_180009986
0x180009992  jmp     loc_180009913
0x180009997  cmp     [rsp+68h+pulProblemNumber], 12h
0x18000999c  jnz     short loc_1800099A2
0x18000999e  mov     edi, ebx
0x1800099a0  jmp     short loc_180009966
0x1800099a2  cmp     [rsp+68h+pulProblemNumber], ebx
0x1800099a6  jnz     loc_18000991C
0x1800099ac  mov     edi, 2
0x1800099b1  jmp     short loc_180009966
0x1800099b3  mov     eax, [rsp+68h+dnDevInst]
0x1800099ba  jmp     short loc_18000995A
0x1800099bc  mov     edi, 3
0x1800099c1  jmp     short loc_180009966
```
