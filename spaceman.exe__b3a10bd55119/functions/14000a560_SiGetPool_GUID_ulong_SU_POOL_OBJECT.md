# SiGetPool(_GUID *,ulong,_SU_POOL_OBJECT * *)

- ea: `0x14000a560`
- end: `0x14000a6c8`
- name: `?SiGetPool@@YAHPEAU_GUID@@KPEAPEAU_SU_POOL_OBJECT@@@Z`
- size: `360`
- prototype: `__int64 __fastcall(struct _GUID *, int, struct _SU_POOL_OBJECT **)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140002c1c`
- `0x140002f20`
- `0x14000a7a8`
- `0x14000c868`

## callees

- `0x14000a560`
- `0x14000d1f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a616`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a634`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a616`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a634`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a5fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a5fb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000a621`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000a621`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000a60e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000a65e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000a60e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000a65e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14000a5ef`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14000a5ef`

## pseudocode

```c
__int64 __fastcall SiGetPool(struct _GUID *a1, int a2, struct _SU_POOL_OBJECT **a3)
{
  DWORD nOutBufferSize; // edi
  __int128 v4; // xmm0
  SIZE_T v6; // rdx
  unsigned int v7; // edi
  char *v8; // rbx
  DWORD BytesReturned; // [rsp+40h] [rbp-58h] BYREF
  int InBuffer; // [rsp+48h] [rbp-50h] BYREF
  __int128 v12; // [rsp+4Ch] [rbp-4Ch]
  GUID v13; // [rsp+5Ch] [rbp-3Ch]
  int v14; // [rsp+6Ch] [rbp-2Ch]

  *a3 = 0;
  nOutBufferSize = 6928;
  v4 = (__int128)*a1;
  v14 = a2;
  v6 = 6984;
  BytesReturned = 0;
  v12 = v4;
  InBuffer = 40;
  v13 = GUID_NULL;
  while ( 1 )
  {
    v8 = (char *)LocalAlloc(0, v6);
    if ( !v8 )
    {
      SetLastError(0x5AAu);
      return 0;
    }
    v7 = DeviceIoControl(Spaceport, 0xE70008u, &InBuffer, 0x28u, v8 + 56, nOutBufferSize, &BytesReturned, 0);
    if ( v7 )
      break;
    if ( GetLastError() != 234 )
    {
      if ( v8 )
        LocalFree(v8);
      return v7;
    }
    nOutBufferSize = *((_DWORD *)v8 + 15);
    LocalFree(v8);
    SetLastError(0);
    v6 = nOutBufferSize + 56;
  }
  if ( v8[2640] )
  {
    *(_OWORD *)(v8 + 2780) = *(_OWORD *)&SuPrimordialTemplates;
    *(_OWORD *)(v8 + 2796) = xmmword_1400142B0;
    *(_OWORD *)(v8 + 2812) = xmmword_1400142C0;
    *(_OWORD *)(v8 + 2828) = xmmword_1400142D0;
    *(_QWORD *)(v8 + 2844) = qword_1400142E0;
  }
  *(_OWORD *)(v8 + 40) = *((_OWORD *)v8 + 4);
  *a3 = (struct _SU_POOL_OBJECT *)v8;
  return v7;
}

```

## disassembly

```asm
0x14000a560  push    rbx
0x14000a562  push    rsi
0x14000a563  push    rdi
0x14000a564  sub     rsp, 80h
0x14000a56b  mov     rax, cs:__security_cookie
0x14000a572  xor     rax, rsp
0x14000a575  mov     [rsp+98h+var_28], rax
0x14000a57a  mov     qword ptr [r8], 0
0x14000a581  mov     edi, 1B10h
0x14000a586  movups  xmm0, xmmword ptr [rcx]
0x14000a589  mov     [rsp+98h+var_2C], edx
0x14000a58d  mov     rsi, r8
0x14000a590  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x14000a597  lea     edx, [rdi+38h]
0x14000a59a  mov     [rsp+98h+BytesReturned], 0
0x14000a5a2  movdqu  [rsp+98h+var_4C], xmm0
0x14000a5a8  mov     [rsp+98h+InBuffer], 28h ; '('
0x14000a5b0  movdqu  [rsp+98h+var_3C], xmm1
0x14000a5b6  jmp     short loc_14000A61F
0x14000a5b8  mov     [rsp+98h+lpOverlapped], 0; lpOverlapped
0x14000a5c1  lea     rax, [rsp+98h+BytesReturned]
0x14000a5c6  mov     [rsp+98h+lpBytesReturned], rax; lpBytesReturned
0x14000a5cb  lea     rcx, [rbx+38h]
0x14000a5cf  mov     [rsp+98h+nOutBufferSize], edi; nOutBufferSize
0x14000a5d3  lea     r8, [rsp+98h+InBuffer]; lpInBuffer
0x14000a5d8  mov     [rsp+98h+lpOutBuffer], rcx; lpOutBuffer
0x14000a5dd  mov     r9d, 28h ; '('; nInBufferSize
0x14000a5e3  mov     rcx, cs:?Spaceport@@3PEAXEA; hDevice
0x14000a5ea  mov     edx, 0E70008h; dwIoControlCode
0x14000a5ef  call    cs:__imp_DeviceIoControl
0x14000a5f5  mov     edi, eax
0x14000a5f7  test    eax, eax
0x14000a5f9  jnz     short loc_14000A666
0x14000a5fb  call    cs:__imp_GetLastError
0x14000a601  cmp     eax, 0EAh
0x14000a606  jnz     short loc_14000A656
0x14000a608  mov     edi, [rbx+3Ch]
0x14000a60b  mov     rcx, rbx; hMem
0x14000a60e  call    cs:__imp_LocalFree
0x14000a614  xor     ecx, ecx; dwErrCode
0x14000a616  call    cs:__imp_SetLastError
0x14000a61c  lea     edx, [rdi+38h]; uBytes
0x14000a61f  xor     ecx, ecx; uFlags
0x14000a621  call    cs:__imp_LocalAlloc
0x14000a627  mov     rbx, rax
0x14000a62a  test    rax, rax
0x14000a62d  jnz     short loc_14000A5B8
0x14000a62f  mov     ecx, 5AAh; dwErrCode
0x14000a634  call    cs:__imp_SetLastError
0x14000a63a  xor     edi, edi
0x14000a63c  mov     eax, edi
0x14000a63e  mov     rcx, [rsp+98h+var_28]
0x14000a643  xor     rcx, rsp; StackCookie
0x14000a646  call    __security_check_cookie
0x14000a64b  add     rsp, 80h
0x14000a652  pop     rdi
0x14000a653  pop     rsi
0x14000a654  pop     rbx
0x14000a655  retn
0x14000a656  test    rbx, rbx
0x14000a659  jz      short loc_14000A63C
0x14000a65b  mov     rcx, rbx; hMem
0x14000a65e  call    cs:__imp_LocalFree
0x14000a664  jmp     short loc_14000A63C
0x14000a666  cmp     byte ptr [rbx+0A50h], 0
0x14000a66d  jz      short loc_14000A6B7
0x14000a66f  movaps  xmm0, cs:?SuPrimordialTemplates@@3PAVSP_RESILIENCY_INFO@@A; SP_RESILIENCY_INFO near * SuPrimordialTemplates
0x14000a676  movups  xmmword ptr [rbx+0ADCh], xmm0
0x14000a67d  movaps  xmm1, cs:xmmword_1400142B0
0x14000a684  movups  xmmword ptr [rbx+0AECh], xmm1
0x14000a68b  movaps  xmm0, cs:xmmword_1400142C0
0x14000a692  movups  xmmword ptr [rbx+0AFCh], xmm0
0x14000a699  movaps  xmm1, cs:xmmword_1400142D0
0x14000a6a0  movups  xmmword ptr [rbx+0B0Ch], xmm1
0x14000a6a7  movsd   xmm0, cs:qword_1400142E0
0x14000a6af  movsd   qword ptr [rbx+0B1Ch], xmm0
0x14000a6b7  movups  xmm0, xmmword ptr [rbx+40h]
0x14000a6bb  movdqu  xmmword ptr [rbx+28h], xmm0
0x14000a6c0  mov     [rsi], rbx
0x14000a6c3  jmp     loc_14000A63C
```
