# CTask::HrRecalculateLastPage(void)

- ea: `0x180023a64`
- end: `0x180023b82`
- name: `?HrRecalculateLastPage@CTask@@AEAAJXZ`
- size: `286`
- prototype: `__int64 __fastcall(CTask *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021b1c`
- `0x180021d04`

## callees

- `0x18000ae04`
- `0x180023a64`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023ae0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023b00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023ae0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023b00`

## pseudocode

```c
__int64 __fastcall CTask::HrRecalculateLastPage(CTask *this)
{
  int v2; // ebx
  _OWORD *i; // rdi
  __int64 v5; // [rsp+50h] [rbp+8h] BYREF
  _OWORD *v6; // [rsp+58h] [rbp+10h] BYREF

  v5 = 0;
  v2 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, __int64 *))(**((_QWORD **)this + 31) + 128LL))(
         *((_QWORD *)this + 31),
         (char *)this + 16,
         0,
         &v5);
  if ( v2 >= 0 )
  {
    v6 = 0;
    for ( i = 0; ; i = v6 )
    {
      v2 = (*(__int64 (__fastcall **)(__int64, __int64, _OWORD **))(*(_QWORD *)v5 + 24LL))(v5, 1, &v6);
      if ( v2 )
        break;
      CoTaskMemFree(i);
    }
    if ( i )
    {
      *(_OWORD *)((char *)this + 156) = *i;
      CoTaskMemFree(i);
    }
    if ( v2 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          50,
          &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
          (unsigned int)v2);
    }
    else
    {
      v2 = 0;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      51,
      &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
      (unsigned int)v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180023a64  mov     [rsp+arg_10], rbx
0x180023a69  push    rbp
0x180023a6a  push    rsi
0x180023a6b  push    rdi
0x180023a6c  sub     rsp, 30h
0x180023a70  mov     rsi, rcx
0x180023a73  mov     [rsp+48h+arg_0], 0
0x180023a7c  mov     rcx, [rcx+0F8h]
0x180023a83  lea     r9, [rsp+48h+arg_0]
0x180023a88  xor     r8d, r8d
0x180023a8b  lea     rdx, [rsi+10h]
0x180023a8f  mov     rax, [rcx]
0x180023a92  mov     rax, [rax+80h]
0x180023a99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a9e  lea     rbp, WPP_GLOBAL_Control
0x180023aa5  mov     ebx, eax
0x180023aa7  test    eax, eax
0x180023aa9  js      loc_180023B49
0x180023aaf  mov     [rsp+48h+arg_8], 0
0x180023ab8  xor     edi, edi
0x180023aba  mov     rcx, [rsp+48h+arg_0]
0x180023abf  lea     r8, [rsp+48h+arg_8]
0x180023ac4  xor     r9d, r9d
0x180023ac7  mov     rax, [rcx]
0x180023aca  lea     edx, [r9+1]
0x180023ace  mov     rax, [rax+18h]
0x180023ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ad7  mov     ebx, eax
0x180023ad9  test    eax, eax
0x180023adb  jnz     short loc_180023AED
0x180023add  mov     rcx, rdi; pv
0x180023ae0  call    cs:__imp_CoTaskMemFree
0x180023ae6  mov     rdi, [rsp+48h+arg_8]
0x180023aeb  jmp     short loc_180023ABA
0x180023aed  test    rdi, rdi
0x180023af0  jz      short loc_180023B06
0x180023af2  movups  xmm0, xmmword ptr [rdi]
0x180023af5  mov     rcx, rdi; pv
0x180023af8  movdqu  xmmword ptr [rsi+9Ch], xmm0
0x180023b00  call    cs:__imp_CoTaskMemFree
0x180023b06  test    ebx, ebx
0x180023b08  js      short loc_180023B0E
0x180023b0a  xor     ebx, ebx
0x180023b0c  jmp     short loc_180023B38
0x180023b0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180023b15  cmp     rcx, rbp
0x180023b18  jz      short loc_180023B38
0x180023b1a  test    byte ptr [rcx+1Ch], 4
0x180023b1e  jz      short loc_180023B38
0x180023b20  mov     rcx, [rcx+10h]
0x180023b24  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x180023b2b  mov     edx, 32h ; '2'
0x180023b30  mov     r9d, ebx
0x180023b33  call    WPP_SF_d
0x180023b38  mov     rcx, [rsp+48h+arg_0]
0x180023b3d  mov     rax, [rcx]
0x180023b40  mov     rax, [rax+10h]
0x180023b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b49  mov     rcx, cs:WPP_GLOBAL_Control
0x180023b50  cmp     rcx, rbp
0x180023b53  jz      short loc_180023B73
0x180023b55  test    byte ptr [rcx+1Ch], 10h
0x180023b59  jz      short loc_180023B73
0x180023b5b  mov     rcx, [rcx+10h]
0x180023b5f  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x180023b66  mov     edx, 33h ; '3'
0x180023b6b  mov     r9d, ebx
0x180023b6e  call    WPP_SF_d
0x180023b73  mov     eax, ebx
0x180023b75  mov     rbx, [rsp+48h+arg_10]
0x180023b7a  add     rsp, 30h
0x180023b7e  pop     rdi
0x180023b7f  pop     rsi
0x180023b80  pop     rbp
0x180023b81  retn
```
