# CCommDeviceControl_RawReadData

- ea: `0x180075580`
- end: `0x180075691`
- name: `CCommDeviceControl_RawReadData`
- size: `273`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001d428`
- `0x180033cc0`
- `0x180075580`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007564b`
- `KERNEL32!GetLastError` at `0x180075658`
- `KERNEL32!GetLastError` at `0x18007564b`
- `KERNEL32!GetLastError` at `0x180075658`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180075641`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180075641`
- `api-ms-win-core-comm-l1-1-0!ClearCommError` at `0x180075615`
- `api-ms-win-core-comm-l1-1-0!ClearCommError` at `0x180075615`

## pseudocode

```c
signed int __fastcall CCommDeviceControl_RawReadData(_QWORD *a1, void *a2, DWORD *a3, struct _OVERLAPPED *a4)
{
  signed int result; // eax
  HANDLE *v9; // rbx
  DWORD cbInQue; // r8d
  DWORD Errors; // [rsp+30h] [rbp-68h] BYREF
  __int128 v12; // [rsp+38h] [rbp-60h] BYREF
  __int128 v13; // [rsp+48h] [rbp-50h]
  _COMSTAT Stat; // [rsp+58h] [rbp-40h] BYREF

  *(_QWORD *)&Stat = 0;
  Stat.cbOutQue = 0;
  v12 = 0;
  Errors = 0;
  v13 = 0;
  result = hresPvVtbl_(a1, off_1800AE180);
  if ( result >= 0 )
  {
    if ( a3 && a2 )
    {
      v9 = (HANDLE *)((char *)a1 - *(int *)(*a1 - 8LL));
      if ( !a4 )
      {
        v12 = 0;
        a4 = (struct _OVERLAPPED *)&v12;
        v13 = 0;
      }
      ClearCommError(v9[69], &Errors, &Stat);
      cbInQue = Stat.cbInQue;
      if ( *a3 < Stat.cbInQue )
        cbInQue = *a3;
      *a3 = cbInQue;
      if ( cbInQue && !ReadFile(v9[69], a2, cbInQue, a3, a4) && GetLastError() == 997 )
      {
        result = GetLastError();
        *((_DWORD *)v9 + 137) = result;
        if ( result > 0 )
          return (unsigned __int16)result | 0x80070000;
      }
      else
      {
        return 0;
      }
    }
    else
    {
      return -2147467261;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180075580  push    rbx
0x180075582  push    rbp
0x180075583  push    rsi
0x180075584  push    rdi
0x180075585  sub     rsp, 78h
0x180075589  mov     rax, cs:__security_cookie
0x180075590  xor     rax, rsp
0x180075593  mov     [rsp+98h+var_30], rax
0x180075598  xor     eax, eax
0x18007559a  xorps   xmm0, xmm0
0x18007559d  mov     rbp, rdx
0x1800755a0  mov     qword ptr [rsp+98h+Stat.fCtsHold], rax
0x1800755a5  lea     rdx, off_1800AE180
0x1800755ac  mov     [rsp+98h+Stat.cbOutQue], eax
0x1800755b0  movups  [rsp+98h+var_60], xmm0
0x1800755b5  mov     [rsp+98h+Errors], eax
0x1800755b9  mov     rsi, r9
0x1800755bc  movups  [rsp+98h+var_50], xmm0
0x1800755c1  mov     rdi, r8
0x1800755c4  mov     rbx, rcx
0x1800755c7  call    _hresPvVtbl_
0x1800755cc  test    eax, eax
0x1800755ce  js      loc_18007567B
0x1800755d4  test    rdi, rdi
0x1800755d7  jz      loc_180075676
0x1800755dd  test    rbp, rbp
0x1800755e0  jz      loc_180075676
0x1800755e6  mov     rax, [rbx]
0x1800755e9  movsxd  rcx, dword ptr [rax-8]
0x1800755ed  sub     rbx, rcx
0x1800755f0  test    rsi, rsi
0x1800755f3  jnz     short loc_180075604
0x1800755f5  movups  [rsp+98h+var_60], xmm0
0x1800755fa  lea     rsi, [rsp+98h+var_60]
0x1800755ff  movups  [rsp+98h+var_50], xmm0
0x180075604  mov     rcx, [rbx+228h]; hFile
0x18007560b  lea     r8, [rsp+98h+Stat]; lpStat
0x180075610  lea     rdx, [rsp+98h+Errors]; lpErrors
0x180075615  call    cs:__imp_ClearCommError
0x18007561b  mov     r8d, [rsp+98h+Stat.cbInQue]
0x180075620  cmp     [rdi], r8d
0x180075623  cmovb   r8d, [rdi]; nNumberOfBytesToRead
0x180075627  mov     [rdi], r8d
0x18007562a  test    r8d, r8d
0x18007562d  jz      short loc_180075672
0x18007562f  mov     rcx, [rbx+228h]; hFile
0x180075636  mov     r9, rdi; lpNumberOfBytesRead
0x180075639  mov     rdx, rbp; lpBuffer
0x18007563c  mov     [rsp+98h+lpOverlapped], rsi; lpOverlapped
0x180075641  call    cs:__imp_ReadFile
0x180075647  test    eax, eax
0x180075649  jnz     short loc_180075672
0x18007564b  call    cs:__imp_GetLastError
0x180075651  cmp     eax, 3E5h
0x180075656  jnz     short loc_180075672
0x180075658  call    cs:__imp_GetLastError
0x18007565e  mov     [rbx+224h], eax
0x180075664  test    eax, eax
0x180075666  jle     short loc_18007567B
0x180075668  movzx   eax, ax
0x18007566b  or      eax, 80070000h
0x180075670  jmp     short loc_18007567B
0x180075672  xor     eax, eax
0x180075674  jmp     short loc_18007567B
0x180075676  mov     eax, 80004003h
0x18007567b  mov     rcx, [rsp+98h+var_30]
0x180075680  xor     rcx, rsp; StackCookie
0x180075683  call    __security_check_cookie
0x180075688  add     rsp, 78h
0x18007568c  pop     rdi
0x18007568d  pop     rsi
0x18007568e  pop     rbp
0x18007568f  pop     rbx
0x180075690  retn
```
