# CControlPacket::AddString(ushort const *,ushort const *,ulong,ushort const *)

- ea: `0x180011e48`
- end: `0x180011f25`
- name: `?AddString@CControlPacket@@QEAAKPEBG0K0@Z`
- size: `221`
- prototype: `unsigned int __fastcall(CControlPacket *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `8`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001231c`
- `0x180012d80`
- `0x180013030`
- `0x1800139a8`
- `0x180014d10`
- `0x180014e68`
- `0x180014f24`
- `0x180014f60`

## callees

- `0x180007ddc`
- `0x1800118fc`
- `0x180011e48`
- `0x180012254`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180011ed0`
- `KERNEL32!SetLastError` at `0x180011ed0`
- `KERNEL32!GetLastError` at `0x180011eb2`
- `KERNEL32!GetLastError` at `0x180011eb2`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x180011ede`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x180011ede`

## pseudocode

```c
unsigned int __fastcall CControlPacket::AddString(
        CControlPacket *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 *Src)
{
  __int64 v9; // rbx
  unsigned __int64 v10; // rbx
  unsigned int v11; // ebp
  unsigned int v12; // esi
  DWORD LastError; // ebx
  int v15; // [rsp+20h] [rbp-48h]

  v9 = -1;
  do
    ++v9;
  while ( Src[v9] );
  v10 = v9 + 1;
  v11 = -1;
  if ( v10 <= 0xFFFFFFFF )
    v11 = v10;
  v12 = v10 > 0xFFFFFFFF ? 0x80070216 : 0;
  ElValidateHrLite_5(v12);
  if ( v10 <= 0xFFFFFFFF )
    return CControlPacket::AddVariable<unsigned short>(this, a2, a3, a4, v15, v11, Src);
  LastError = GetLastError();
  if ( (g_uErrLibFlags & 1) != 0 )
    ElTraceErrorInfo();
  SetLastError(LastError);
  return WIN32_FROM_HRESULT(v12);
}

```

## disassembly

```asm
0x180011e48  mov     [rsp+arg_0], rbx
0x180011e4d  mov     [rsp+arg_8], rbp
0x180011e52  mov     [rsp+arg_10], rsi
0x180011e57  push    rdi
0x180011e58  push    r12
0x180011e5a  push    r13
0x180011e5c  push    r14
0x180011e5e  push    r15
0x180011e60  sub     rsp, 40h
0x180011e64  mov     rdi, [rsp+68h+arg_20]
0x180011e6c  mov     r14d, r9d
0x180011e6f  mov     r15, r8
0x180011e72  mov     r12, rdx
0x180011e75  mov     r13, rcx
0x180011e78  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180011e7c  inc     rbx
0x180011e7f  cmp     word ptr [rdi+rbx*2], 0
0x180011e84  jnz     short loc_180011E7C
0x180011e86  mov     eax, 0FFFFFFFFh
0x180011e8b  inc     rbx
0x180011e8e  cmp     rbx, rax
0x180011e91  mov     ebp, eax
0x180011e93  cmovbe  ebp, ebx
0x180011e96  cmp     rax, rbx
0x180011e99  sbb     esi, esi
0x180011e9b  and     esi, 80070216h
0x180011ea1  mov     ecx, esi
0x180011ea3  call    ElValidateHrLite_5
0x180011ea8  mov     eax, 0FFFFFFFFh
0x180011ead  cmp     rbx, rax
0x180011eb0  jbe     short loc_180011EEC
0x180011eb2  call    cs:__imp_GetLastError
0x180011eb9  nop     dword ptr [rax+rax+00h]
0x180011ebe  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x180011ec5  mov     ebx, eax
0x180011ec7  jz      short loc_180011ECE
0x180011ec9  call    ElTraceErrorInfo
0x180011ece  mov     ecx, ebx; dwErrCode
0x180011ed0  call    cs:__imp_SetLastError
0x180011ed7  nop     dword ptr [rax+rax+00h]
0x180011edc  mov     ecx, esi
0x180011ede  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180011ee5  nop     dword ptr [rax+rax+00h]
0x180011eea  jmp     short loc_180011F06
0x180011eec  mov     [rsp+68h+Src], rdi; Src
0x180011ef1  mov     r9d, r14d; int
0x180011ef4  mov     r8, r15; int
0x180011ef7  mov     [rsp+68h+var_40], ebp; int
0x180011efb  mov     rdx, r12; int
0x180011efe  mov     rcx, r13; int
0x180011f01  call    ??$AddVariable@G@CControlPacket@@QEAAKPEBG0KKKPEAX@Z; CControlPacket::AddVariable<ushort>(ushort const *,ushort const *,ulong,ulong,ulong,void *)
0x180011f06  lea     r11, [rsp+68h+var_28]
0x180011f0b  mov     rbx, [r11+30h]
0x180011f0f  mov     rbp, [r11+38h]
0x180011f13  mov     rsi, [r11+40h]
0x180011f17  mov     rsp, r11
0x180011f1a  pop     r15
0x180011f1c  pop     r14
0x180011f1e  pop     r13
0x180011f20  pop     r12
0x180011f22  pop     rdi
0x180011f23  retn
```
