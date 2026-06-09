# CWorkItem::HrStart(int)

- ea: `0x180001798`
- end: `0x180001816`
- name: `?HrStart@CWorkItem@@QEAAJH@Z`
- size: `126`
- prototype: `__int64 __fastcall(_DWORD *pv)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000168c`
- `0x18002f5d8`

## callees

- `0x180001798`
- `0x18000554c`
- `0x18002f028`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800017bf`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800017bf`

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
0x180001798  mov     [rsp+arg_0], rbx
0x18000179d  push    rdi
0x18000179e  sub     rsp, 30h
0x1800017a2  mov     rdi, rcx
0x1800017a5  mov     dword ptr [rcx+8], 1
0x1800017ac  mov     rdx, rcx; pv
0x1800017af  lea     r8, pcbe; pcbe
0x1800017b6  lea     rcx, ?ThreadPoolCallback@CWorkItem@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x1800017bd  xor     ebx, ebx
0x1800017bf  call    cs:__imp_TrySubmitThreadpoolCallback
0x1800017c5  test    eax, eax
0x1800017c7  jnz     short loc_180001809
0x1800017c9  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800017ce  mov     ebx, eax
0x1800017d0  test    eax, eax
0x1800017d2  jz      short loc_180001809
0x1800017d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800017db  lea     rax, WPP_GLOBAL_Control
0x1800017e2  cmp     rcx, rax
0x1800017e5  jz      short loc_180001809
0x1800017e7  test    byte ptr [rcx+1Ch], 1
0x1800017eb  jz      short loc_180001809
0x1800017ed  mov     rcx, [rcx+10h]
0x1800017f1  lea     r8, WPP_d99cd052381a3366086b95fac24ae15e_Traceguids
0x1800017f8  mov     edx, 0Ah
0x1800017fd  mov     [rsp+38h+var_18], ebx
0x180001801  mov     r9, rdi
0x180001804  call    WPP_SF_qd
0x180001809  mov     eax, ebx
0x18000180b  mov     rbx, [rsp+38h+arg_0]
0x180001810  add     rsp, 30h
0x180001814  pop     rdi
0x180001815  retn
```
