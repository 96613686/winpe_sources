# CWorkItem::HrStart(int)

- ea: `0x180014aa4`
- end: `0x180014b29`
- name: `?HrStart@CWorkItem@@QEAAJH@Z`
- size: `133`
- prototype: `__int64 __fastcall(PVOID pv, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180014988`
- `0x180031898`

## callees

- `0x18000683c`
- `0x180014aa4`
- `0x180031278`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180014acb`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180014acb`

## pseudocode

```c
__int64 __fastcall CWorkItem::HrStart(_DWORD *pv)
{
  unsigned int Win32Error; // ebx

  pv[2] = 1;
  Win32Error = 0;
  if ( !TrySubmitThreadpoolCallback(CWorkItem::ThreadPoolCallback, pv, &pcbe) )
  {
    Win32Error = HrFromLastWin32Error();
    if ( Win32Error )
    {
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
        WPP_SF_qd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_d99cd052381a3366086b95fac24ae15e_Traceguids,
          pv,
          Win32Error);
    }
  }
  return Win32Error;
}

```

## disassembly

```asm
0x180014aa4  mov     [rsp+arg_0], rbx
0x180014aa9  push    rdi
0x180014aaa  sub     rsp, 30h
0x180014aae  mov     rdi, rcx
0x180014ab1  mov     dword ptr [rcx+8], 1
0x180014ab8  mov     rdx, rcx; pv
0x180014abb  lea     r8, pcbe; pcbe
0x180014ac2  lea     rcx, ?ThreadPoolCallback@CWorkItem@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x180014ac9  xor     ebx, ebx
0x180014acb  call    cs:__imp_TrySubmitThreadpoolCallback
0x180014ad2  nop     dword ptr [rax+rax+00h]
0x180014ad7  test    eax, eax
0x180014ad9  jnz     short loc_180014B1B
0x180014adb  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180014ae0  mov     ebx, eax
0x180014ae2  test    eax, eax
0x180014ae4  jz      short loc_180014B1B
0x180014ae6  mov     rcx, cs:WPP_GLOBAL_Control
0x180014aed  lea     rax, WPP_GLOBAL_Control
0x180014af4  cmp     rcx, rax
0x180014af7  jz      short loc_180014B1B
0x180014af9  test    byte ptr [rcx+1Ch], 1
0x180014afd  jz      short loc_180014B1B
0x180014aff  mov     rcx, [rcx+10h]
0x180014b03  lea     r8, WPP_d99cd052381a3366086b95fac24ae15e_Traceguids
0x180014b0a  mov     edx, 0Ah
0x180014b0f  mov     [rsp+38h+var_18], ebx
0x180014b13  mov     r9, rdi
0x180014b16  call    WPP_SF_qd
0x180014b1b  mov     eax, ebx
0x180014b1d  mov     rbx, [rsp+38h+arg_0]
0x180014b22  add     rsp, 30h
0x180014b26  pop     rdi
0x180014b27  retn
```
