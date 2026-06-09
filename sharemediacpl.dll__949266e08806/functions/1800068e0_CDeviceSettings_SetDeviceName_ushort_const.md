# CDeviceSettings::SetDeviceName(ushort const *)

- ea: `0x1800068e0`
- end: `0x1800069cb`
- name: `?SetDeviceName@CDeviceSettings@@QEAAJPEBG@Z`
- size: `235`
- prototype: `int(CDeviceSettings *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800087c0`

## callees

- `0x180003860`
- `0x180003888`
- `0x1800068e0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180006972`
- `ole32!CoTaskMemFree` at `0x180006972`
- `SHLWAPI!SHStrDupW` at `0x18000697f`
- `SHLWAPI!SHStrDupW` at `0x18000697f`

## pseudocode

```c
__int64 __fastcall CDeviceSettings::SetDeviceName(LPVOID *this, const unsigned __int16 *a2)
{
  _QWORD *v4; // r10
  const unsigned __int16 *v5; // rax
  __int64 v6; // r8
  HRESULT v7; // eax
  unsigned int v8; // ebx

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
    goto LABEL_10;
  v5 = a2;
  v6 = 0x7FFFFFFF;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v6;
  }
  while ( v6 );
  if ( (v6 != 0 ? 0x7FFFFFFF - (_DWORD)v6 : 0) != 0 )
  {
    CoTaskMemFree(this[9]);
    v7 = SHStrDupW(a2, (LPWSTR *)this + 9);
    v4 = WPP_GLOBAL_Control;
    v8 = v7;
  }
  else
  {
LABEL_10:
    v8 = -2147024809;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
    WPP_SF_d(v4[2], 63, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x1800068e0  mov     [rsp+arg_0], rbx
0x1800068e5  mov     [rsp+arg_8], rsi
0x1800068ea  push    rdi
0x1800068eb  sub     rsp, 20h
0x1800068ef  mov     rdi, rdx
0x1800068f2  mov     rbx, rcx
0x1800068f5  mov     r10, cs:WPP_GLOBAL_Control
0x1800068fc  lea     rsi, WPP_GLOBAL_Control
0x180006903  cmp     r10, rsi
0x180006906  jz      short loc_18000692B
0x180006908  test    byte ptr [r10+1Ch], 20h
0x18000690d  jz      short loc_18000692B
0x18000690f  mov     rcx, [r10+10h]
0x180006913  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x18000691a  mov     edx, 3Eh ; '>'
0x18000691f  call    WPP_SF_
0x180006924  mov     r10, cs:WPP_GLOBAL_Control
0x18000692b  xor     ecx, ecx
0x18000692d  test    rdi, rdi
0x180006930  jz      short loc_180006990
0x180006932  mov     r9d, 7FFFFFFFh
0x180006938  mov     rax, rdi
0x18000693b  mov     r8d, r9d
0x18000693e  cmp     [rax], cx
0x180006941  jz      short loc_18000694D
0x180006943  add     rax, 2
0x180006947  sub     r8, 1
0x18000694b  jnz     short loc_18000693E
0x18000694d  sub     r9d, r8d
0x180006950  mov     rax, r8
0x180006953  neg     rax
0x180006956  mov     rdx, r8
0x180006959  sbb     ecx, ecx
0x18000695b  and     ecx, r9d
0x18000695e  neg     rdx
0x180006961  sbb     edx, edx
0x180006963  and     edx, ecx
0x180006965  neg     r8
0x180006968  sbb     eax, eax
0x18000696a  test    edx, eax
0x18000696c  jbe     short loc_180006990
0x18000696e  mov     rcx, [rbx+48h]; pv
0x180006972  call    cs:__imp_CoTaskMemFree
0x180006978  lea     rdx, [rbx+48h]; ppwsz
0x18000697c  mov     rcx, rdi; psz
0x18000697f  call    cs:__imp_SHStrDupW
0x180006985  mov     r10, cs:WPP_GLOBAL_Control
0x18000698c  mov     ebx, eax
0x18000698e  jmp     short loc_180006995
0x180006990  mov     ebx, 80070057h
0x180006995  cmp     r10, rsi
0x180006998  jz      short loc_1800069B9
0x18000699a  test    byte ptr [r10+1Ch], 20h
0x18000699f  jz      short loc_1800069B9
0x1800069a1  mov     rcx, [r10+10h]
0x1800069a5  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x1800069ac  mov     edx, 3Fh ; '?'
0x1800069b1  mov     r9d, ebx
0x1800069b4  call    WPP_SF_d
0x1800069b9  mov     rsi, [rsp+28h+arg_8]
0x1800069be  mov     eax, ebx
0x1800069c0  mov     rbx, [rsp+28h+arg_0]
0x1800069c5  add     rsp, 20h
0x1800069c9  pop     rdi
0x1800069ca  retn
```
