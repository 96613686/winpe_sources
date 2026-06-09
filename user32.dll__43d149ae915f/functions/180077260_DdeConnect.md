# DdeConnect

- ea: `0x180077260`
- end: `0x18007735b`
- name: `DdeConnect`
- size: `251`
- prototype: `HCONV __stdcall(DWORD idInst, HSZ hszService, HSZ hszTopic, PCONVCONTEXT pCC)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x180046604`
- `0x180048320`
- `0x180076dd0`
- `0x180077260`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180077297`
- `ntdll!RtlEnterCriticalSection` at `0x180077297`
- `ntdll!RtlLeaveCriticalSection` at `0x180077347`
- `ntdll!RtlLeaveCriticalSection` at `0x180077347`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007733a`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007733a`

## pseudocode

```c
HCONV __stdcall DdeConnect(DWORD idInst, HSZ hszService, HSZ hszTopic, PCONVCONTEXT pCC)
{
  void *v4; // rbx
  HCONV v5; // rdi
  struct tagCL_INSTANCE_INFO *v7; // rbx
  HWND v8; // rax
  struct tagCL_CONV_INFO *v9; // rax
  struct tagCL_INSTANCE_INFO *v11; // [rsp+40h] [rbp-10h] BYREF
  HWND v12; // [rsp+48h] [rbp-8h] BYREF
  unsigned __int16 v13; // [rsp+80h] [rbp+30h] BYREF
  HSZ v14; // [rsp+88h] [rbp+38h] BYREF
  struct tagCONVCONTEXT *v15; // [rsp+98h] [rbp+48h] BYREF

  v15 = pCC;
  v14 = hszService;
  v4 = (void *)(int)idInst;
  v11 = 0;
  v5 = 0;
  v12 = 0;
  v13 = 0;
  RtlEnterCriticalSection(&gcsDDEML);
  if ( ValidateConnectParameters(v4, &v11, &v14, hszTopic, &v13, &v15, &v12, 0) )
  {
    v7 = v11;
    if ( (*((_DWORD *)v11 + 14) & 0x1000) != 0 )
      v8 = (HWND)*((_QWORD *)v11 + 4);
    else
      v8 = 0;
    v9 = ConnectConv(v11, (unsigned __int16)v14, (unsigned __int16)hszTopic, v12, v8, v15, 0, 1u);
    if ( v9 )
      v5 = (HCONV)*((_QWORD *)v9 + 3);
    else
      SetLastDDEMLError(v7, 0x400Au);
  }
  if ( v13 )
    GlobalDeleteAtom(v13);
  RtlLeaveCriticalSection(&gcsDDEML);
  return v5;
}

```

## disassembly

```asm
0x180077260  mov     [rsp-28h+arg_18], r9
0x180077265  mov     [rsp-28h+arg_8], rdx
0x18007726a  push    rbp
0x18007726b  push    rbx
0x18007726c  push    rsi
0x18007726d  push    rdi
0x18007726e  push    r14
0x180077270  mov     rbp, rsp
0x180077273  sub     rsp, 50h
0x180077277  xor     r14d, r14d
0x18007727a  movsxd  rbx, ecx
0x18007727d  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180077284  mov     [rbp+var_10], r14
0x180077288  mov     edi, r14d
0x18007728b  mov     [rbp+var_8], r14
0x18007728f  mov     [rbp+arg_0], r14w
0x180077294  mov     rsi, r8
0x180077297  call    cs:__imp_RtlEnterCriticalSection
0x18007729d  mov     [rsp+50h+var_18], r14; HCONVLIST
0x1800772a2  lea     rax, [rbp+var_8]
0x1800772a6  mov     [rsp+50h+var_20], rax; HWND *
0x1800772ab  lea     r8, [rbp+arg_8]; HSZ *
0x1800772af  lea     rax, [rbp+arg_18]
0x1800772b3  mov     rcx, rbx; void *
0x1800772b6  mov     [rsp+50h+var_28], rax; struct tagCONVCONTEXT **
0x1800772bb  lea     rdx, [rbp+var_10]; struct tagCL_INSTANCE_INFO **
0x1800772bf  lea     rax, [rbp+arg_0]
0x1800772c3  mov     r9, rsi; HSZ
0x1800772c6  mov     [rsp+50h+var_30], rax; unsigned __int16 *
0x1800772cb  call    ?ValidateConnectParameters@@YAHPEAXPEAPEAUtagCL_INSTANCE_INFO@@PEAPEAUHSZ__@@PEAU2@PEAGPEAPEAUtagCONVCONTEXT@@PEAPEAUHWND__@@PEAUHCONVLIST__@@@Z; ValidateConnectParameters(void *,tagCL_INSTANCE_INFO * *,HSZ__ * *,HSZ__ *,ushort *,tagCONVCONTEXT * *,HWND__ * *,HCONVLIST__ *)
0x1800772d0  test    eax, eax
0x1800772d2  jz      short loc_180077331
0x1800772d4  mov     rbx, [rbp+var_10]
0x1800772d8  mov     rcx, [rbp+arg_18]
0x1800772dc  test    dword ptr [rbx+38h], 1000h
0x1800772e3  jz      short loc_1800772EB
0x1800772e5  mov     rax, [rbx+20h]
0x1800772e9  jmp     short loc_1800772EE
0x1800772eb  mov     rax, r14
0x1800772ee  mov     r9, [rbp+var_8]; HWND
0x1800772f2  movzx   r8d, si; unsigned __int16
0x1800772f6  movzx   edx, word ptr [rbp+arg_8]; unsigned __int16
0x1800772fa  mov     dword ptr [rsp+50h+var_18], 1; unsigned int
0x180077302  mov     [rsp+50h+var_20], r14; HCONVLIST
0x180077307  mov     [rsp+50h+var_28], rcx; struct tagCONVCONTEXT *
0x18007730c  mov     rcx, rbx; struct tagCL_INSTANCE_INFO *
0x18007730f  mov     [rsp+50h+var_30], rax; HWND
0x180077314  call    ?ConnectConv@@YAPEAUtagCL_CONV_INFO@@PEAUtagCL_INSTANCE_INFO@@GGPEAUHWND__@@1PEAUtagCONVCONTEXT@@PEAUHCONVLIST__@@K@Z; ConnectConv(tagCL_INSTANCE_INFO *,ushort,ushort,HWND__ *,HWND__ *,tagCONVCONTEXT *,HCONVLIST__ *,ulong)
0x180077319  test    rax, rax
0x18007731c  jnz     short loc_18007732D
0x18007731e  mov     edx, 400Ah; unsigned int
0x180077323  mov     rcx, rbx; struct tagCL_INSTANCE_INFO *
0x180077326  call    ?SetLastDDEMLError@@YAXPEAUtagCL_INSTANCE_INFO@@K@Z; SetLastDDEMLError(tagCL_INSTANCE_INFO *,ulong)
0x18007732b  jmp     short loc_180077331
0x18007732d  mov     rdi, [rax+18h]
0x180077331  movzx   ecx, [rbp+arg_0]; nAtom
0x180077335  test    cx, cx
0x180077338  jz      short loc_180077340
0x18007733a  call    cs:__imp_GlobalDeleteAtom
0x180077340  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180077347  call    cs:__imp_RtlLeaveCriticalSection
0x18007734d  mov     rax, rdi
0x180077350  add     rsp, 50h
0x180077354  pop     r14
0x180077356  pop     rdi
0x180077357  pop     rsi
0x180077358  pop     rbx
0x180077359  pop     rbp
0x18007735a  retn
```
