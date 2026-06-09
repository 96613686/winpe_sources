# PnPHelper::_GetDeviceInstance(ushort const *,ulong *,_GUID *,ulong *)

- ea: `0x180015490`
- end: `0x1800156cc`
- name: `?_GetDeviceInstance@PnPHelper@@YAJPEBGPEAKPEAU_GUID@@1@Z`
- size: `572`
- prototype: `__int64 __fastcall(const wchar_t *this, unsigned __int16 *, unsigned int *, struct _GUID *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18002d15c`
- `0x18002e738`

## callees

- `0x1800140f0`
- `0x180015490`
- `0x180032c90`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800154d3`
- `msvcrt!_wcsicmp` at `0x1800154d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015579`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015630`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015579`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015630`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001563e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001563e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001558d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001558d`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18001562a`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18001562a`
- `DEVOBJ!DevObjOpenDeviceInterface` at `0x180015556`
- `DEVOBJ!DevObjOpenDeviceInterface` at `0x180015556`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180015658`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180015658`
- `DEVOBJ!DevObjDeleteDeviceInterfaceData` at `0x18001564f`
- `DEVOBJ!DevObjDeleteDeviceInterfaceData` at `0x18001564f`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1800155d3`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1800155d3`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18001551d`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18001551d`

## pseudocode

```c
__int64 __fastcall PnPHelper::_GetDeviceInstance(
        const wchar_t *this,
        unsigned __int16 *a2,
        unsigned int *a3,
        struct _GUID *a4)
{
  __int128 v8; // xmm0
  __int64 result; // rax
  int v10; // edi
  __int64 DeviceInfoList; // rax
  __int64 v12; // rbx
  HANDLE ProcessHeap; // rax
  _DWORD *v14; // rax
  void *v15; // rdi
  __int128 v16; // xmm0
  HANDLE v17; // rax
  bool v18; // sf
  __int128 v19; // xmm0
  int v20; // [rsp+40h] [rbp-98h] BYREF
  int v21; // [rsp+44h] [rbp-94h] BYREF
  _OWORD v22[2]; // [rsp+48h] [rbp-90h] BYREF
  __int128 v23; // [rsp+68h] [rbp-70h] BYREF
  __int128 v24; // [rsp+78h] [rbp-60h]
  __int128 v25; // [rsp+88h] [rbp-50h]

  if ( a4 )
    a4->Data1 = 0;
  if ( !_wcsicmp(&String1, this) )
  {
    v8 = xmmword_18003FCB8;
    *(_DWORD *)a2 = dword_18003FCB4;
    result = 0;
    *(_OWORD *)a3 = v8;
    return result;
  }
  v10 = -2147467259;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  *(_DWORD *)a2 = 0;
  v12 = DeviceInfoList;
  if ( DeviceInfoList == -1 )
    goto LABEL_16;
  memset(v22, 0, sizeof(v22));
  LODWORD(v22[0]) = 32;
  if ( (unsigned int)DevObjOpenDeviceInterface(DeviceInfoList, this, 0, v22) )
  {
    v23 = 0;
    v24 = 0;
    v25 = 0;
    ProcessHeap = GetProcessHeap();
    v14 = HeapAlloc(ProcessHeap, 8u, 0x210u);
    v15 = v14;
    if ( v14 )
    {
      *v14 = 8;
      LODWORD(v23) = 48;
      if ( (unsigned int)DevObjGetDeviceInterfaceDetail(v12, v22, v14, 528, 0, &v23) )
      {
        v16 = *(_OWORD *)((char *)v22 + 4);
        *(_DWORD *)a2 = DWORD1(v24);
        *(_OWORD *)a3 = v16;
      }
      v21 = 7;
      v20 = 0;
      ((void (__fastcall *)(__int64, __int128 *, const DEVPROPKEY *, int *, struct _GUID *, int, int *, _DWORD))DevObjGetDeviceProperty)(
        v12,
        &v23,
        &DEVPKEY_Device_SessionId,
        &v21,
        a4,
        4,
        &v20,
        0);
      v17 = GetProcessHeap();
      HeapFree(v17, 0, v15);
      v10 = 0;
    }
    else
    {
      v10 = -2147024882;
    }
    DevObjDeleteDeviceInterfaceData(v12, v22);
  }
  DevObjDestroyDeviceInfoList(v12);
  if ( v10 < 0 )
  {
LABEL_16:
    result = (unsigned int)v10;
  }
  else
  {
    v18 = (int)StringCchCopyW(&String1, 0x104u, this) < 0;
    result = (unsigned int)v10;
    if ( !v18 )
    {
      v19 = *(_OWORD *)a3;
      dword_18003FCB4 = *(_DWORD *)a2;
      xmmword_18003FCB8 = v19;
      return result;
    }
  }
  String1 = 0;
  return result;
}

```

## disassembly

```asm
0x180015490  push    rbp
0x180015492  push    rsi
0x180015493  push    r12
0x180015495  push    r14
0x180015497  push    r15
0x180015499  sub     rsp, 0B0h
0x1800154a0  mov     rax, cs:__security_cookie
0x1800154a7  xor     rax, rsp
0x1800154aa  mov     [rsp+0D8h+var_40], rax
0x1800154b2  xor     r12d, r12d
0x1800154b5  mov     r14, r9
0x1800154b8  mov     rbp, r8
0x1800154bb  mov     r15, rdx
0x1800154be  mov     rsi, rcx
0x1800154c1  test    r9, r9
0x1800154c4  jz      short loc_1800154C9
0x1800154c6  mov     [r9], r12d
0x1800154c9  mov     rdx, rsi; String2
0x1800154cc  lea     rcx, String1; String1
0x1800154d3  call    cs:__imp__wcsicmp
0x1800154d9  test    eax, eax
0x1800154db  jnz     short loc_1800154F9
0x1800154dd  mov     eax, cs:dword_18003FCB4
0x1800154e3  movups  xmm0, cs:xmmword_18003FCB8
0x1800154ea  mov     [r15], eax
0x1800154ed  mov     eax, r12d
0x1800154f0  movups  xmmword ptr [rbp+0], xmm0
0x1800154f4  jmp     loc_1800156AC
0x1800154f9  mov     [rsp+0D8h+var_30], rbx
0x180015501  xor     r9d, r9d
0x180015504  mov     [rsp+0D8h+var_38], rdi
0x18001550c  xor     r8d, r8d
0x18001550f  xor     edx, edx
0x180015511  mov     [rsp+0D8h+var_B8], r12
0x180015516  xor     ecx, ecx
0x180015518  mov     edi, 80004005h
0x18001551d  call    cs:__imp_DevObjCreateDeviceInfoList
0x180015523  mov     [r15], r12d
0x180015526  mov     rbx, rax
0x180015529  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001552d  jz      loc_180015692
0x180015533  xorps   xmm0, xmm0
0x180015536  lea     r9, [rsp+0D8h+var_90]
0x18001553b  movups  [rsp+0D8h+var_90], xmm0
0x180015540  xor     r8d, r8d
0x180015543  mov     dword ptr [rsp+0D8h+var_90], 20h ; ' '
0x18001554b  mov     rdx, rsi
0x18001554e  mov     rcx, rax
0x180015551  movups  [rsp+0D8h+var_80], xmm0
0x180015556  call    cs:__imp_DevObjOpenDeviceInterface
0x18001555c  test    eax, eax
0x18001555e  jz      loc_180015655
0x180015564  xorps   xmm0, xmm0
0x180015567  movups  [rsp+0D8h+var_70], xmm0
0x18001556c  movups  [rsp+0D8h+var_60], xmm0
0x180015571  movups  [rsp+0D8h+var_50], xmm0
0x180015579  call    cs:__imp_GetProcessHeap
0x18001557f  mov     edx, 8; dwFlags
0x180015584  mov     r8d, 210h; dwBytes
0x18001558a  mov     rcx, rax; hHeap
0x18001558d  call    cs:__imp_HeapAlloc
0x180015593  mov     rdi, rax
0x180015596  test    rax, rax
0x180015599  jnz     short loc_1800155A5
0x18001559b  mov     edi, 8007000Eh
0x1800155a0  jmp     loc_180015647
0x1800155a5  mov     dword ptr [rax], 8
0x1800155ab  lea     rdx, [rsp+0D8h+var_90]
0x1800155b0  lea     rax, [rsp+0D8h+var_70]
0x1800155b5  mov     dword ptr [rsp+0D8h+var_70], 30h ; '0'
0x1800155bd  mov     [rsp+0D8h+var_B0], rax
0x1800155c2  mov     r9d, 210h
0x1800155c8  mov     r8, rdi
0x1800155cb  mov     [rsp+0D8h+var_B8], r12
0x1800155d0  mov     rcx, rbx
0x1800155d3  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x1800155d9  test    eax, eax
0x1800155db  jz      short loc_1800155ED
0x1800155dd  movups  xmm0, [rsp+0D8h+var_90+4]
0x1800155e2  mov     eax, dword ptr [rsp+0D8h+var_60+4]
0x1800155e6  mov     [r15], eax
0x1800155e9  movups  xmmword ptr [rbp+0], xmm0
0x1800155ed  mov     [rsp+0D8h+var_A0], r12d
0x1800155f2  lea     rax, [rsp+0D8h+var_98]
0x1800155f7  mov     [rsp+0D8h+var_A8], rax
0x1800155fc  lea     r9, [rsp+0D8h+var_94]
0x180015601  mov     dword ptr [rsp+0D8h+var_B0], 4
0x180015609  lea     r8, DEVPKEY_Device_SessionId
0x180015610  lea     rdx, [rsp+0D8h+var_70]
0x180015615  mov     [rsp+0D8h+var_B8], r14
0x18001561a  mov     rcx, rbx
0x18001561d  mov     [rsp+0D8h+var_94], 7
0x180015625  mov     [rsp+0D8h+var_98], r12d
0x18001562a  call    cs:__imp_DevObjGetDeviceProperty
0x180015630  call    cs:__imp_GetProcessHeap
0x180015636  mov     r8, rdi; lpMem
0x180015639  xor     edx, edx; dwFlags
0x18001563b  mov     rcx, rax; hHeap
0x18001563e  call    cs:__imp_HeapFree
0x180015644  mov     edi, r12d
0x180015647  lea     rdx, [rsp+0D8h+var_90]
0x18001564c  mov     rcx, rbx
0x18001564f  call    cs:__imp_DevObjDeleteDeviceInterfaceData
0x180015655  mov     rcx, rbx
0x180015658  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18001565e  test    edi, edi
0x180015660  js      short loc_180015692
0x180015662  mov     r8, rsi; unsigned __int16 *
0x180015665  lea     rcx, String1; unsigned __int16 *
0x18001566c  mov     edx, 104h; unsigned __int64
0x180015671  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180015676  test    eax, eax
0x180015678  mov     eax, edi
0x18001567a  js      short loc_180015694
0x18001567c  movups  xmm0, xmmword ptr [rbp+0]
0x180015680  mov     ecx, [r15]
0x180015683  mov     cs:dword_18003FCB4, ecx
0x180015689  movups  cs:xmmword_18003FCB8, xmm0
0x180015690  jmp     short loc_18001569C
0x180015692  mov     eax, edi
0x180015694  mov     cs:String1, r12w
0x18001569c  mov     rbx, [rsp+0D8h+var_30]
0x1800156a4  mov     rdi, [rsp+0D8h+var_38]
0x1800156ac  mov     rcx, [rsp+0D8h+var_40]
0x1800156b4  xor     rcx, rsp; StackCookie
0x1800156b7  call    __security_check_cookie
0x1800156bc  add     rsp, 0B0h
0x1800156c3  pop     r15
0x1800156c5  pop     r14
0x1800156c7  pop     r12
0x1800156c9  pop     rsi
0x1800156ca  pop     rbp
0x1800156cb  retn
```
