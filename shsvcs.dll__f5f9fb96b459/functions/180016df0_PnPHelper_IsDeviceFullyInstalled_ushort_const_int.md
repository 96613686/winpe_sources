# PnPHelper::IsDeviceFullyInstalled(ushort const *,int *)

- ea: `0x180016df0`
- end: `0x180016f8d`
- name: `?IsDeviceFullyInstalled@PnPHelper@@YAJPEBGPEAH@Z`
- size: `413`
- prototype: `__int64 __fastcall(PnPHelper *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x18002c270`

## callees

- `0x180016df0`
- `0x180032c90`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016e8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016f36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016e8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016f36`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016f44`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016f44`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016ea3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016ea3`
- `DEVOBJ!DevObjOpenDeviceInterface` at `0x180016e6c`
- `DEVOBJ!DevObjOpenDeviceInterface` at `0x180016e6c`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x180016f1f`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x180016f1f`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180016f5d`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180016f5d`
- `DEVOBJ!DevObjDeleteDeviceInterfaceData` at `0x180016f54`
- `DEVOBJ!DevObjDeleteDeviceInterfaceData` at `0x180016f54`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180016ee9`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180016ee9`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180016e33`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180016e33`

## pseudocode

```c
__int64 __fastcall PnPHelper::IsDeviceFullyInstalled(PnPHelper *this, unsigned __int16 *a2, int *a3)
{
  unsigned int v5; // edi
  __int64 DeviceInfoList; // rax
  __int64 v7; // rbx
  HANDLE ProcessHeap; // rax
  _DWORD *v9; // rax
  void *v10; // rdi
  HANDLE v11; // rax
  int v13; // [rsp+40h] [rbp-78h] BYREF
  _OWORD v14[2]; // [rsp+48h] [rbp-70h] BYREF
  _OWORD v15[3]; // [rsp+68h] [rbp-50h] BYREF

  v5 = -2147467259;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  *(_DWORD *)a2 = 0;
  v7 = DeviceInfoList;
  if ( DeviceInfoList != -1 )
  {
    memset(v14, 0, sizeof(v14));
    LODWORD(v14[0]) = 32;
    if ( (unsigned int)DevObjOpenDeviceInterface(DeviceInfoList, this, 0, v14) )
    {
      memset(v15, 0, sizeof(v15));
      ProcessHeap = GetProcessHeap();
      v9 = HeapAlloc(ProcessHeap, 8u, 0x210u);
      v10 = v9;
      if ( v9 )
      {
        *v9 = 8;
        LODWORD(v15[0]) = 48;
        if ( (unsigned int)DevObjGetDeviceInterfaceDetail(v7, v14, v9, 528, 0, v15) )
        {
          v13 = 0;
          if ( (unsigned int)DevObjGetDeviceRegistryProperty(v7, v15, 34, 0, &v13, 4, 0) )
          {
            if ( !v13 )
              *(_DWORD *)a2 = 1;
          }
        }
        v11 = GetProcessHeap();
        HeapFree(v11, 0, v10);
        v5 = 0;
      }
      else
      {
        v5 = -2147024882;
      }
      DevObjDeleteDeviceInterfaceData(v7, v14);
    }
    DevObjDestroyDeviceInfoList(v7);
  }
  return v5;
}

```

## disassembly

```asm
0x180016df0  mov     [rsp+arg_10], rbx
0x180016df5  mov     [rsp+arg_18], rbp
0x180016dfa  push    rsi
0x180016dfb  push    rdi
0x180016dfc  push    r14
0x180016dfe  sub     rsp, 0A0h
0x180016e05  mov     rax, cs:__security_cookie
0x180016e0c  xor     rax, rsp
0x180016e0f  mov     [rsp+0B8h+var_20], rax
0x180016e17  mov     r14, rdx
0x180016e1a  mov     rsi, rcx
0x180016e1d  xor     ebp, ebp
0x180016e1f  xor     edx, edx
0x180016e21  xor     ecx, ecx
0x180016e23  mov     [rsp+0B8h+var_98], rbp
0x180016e28  xor     r9d, r9d
0x180016e2b  xor     r8d, r8d
0x180016e2e  mov     edi, 80004005h
0x180016e33  call    cs:__imp_DevObjCreateDeviceInfoList
0x180016e39  mov     [r14], ebp
0x180016e3c  mov     rbx, rax
0x180016e3f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180016e43  jz      loc_180016F63
0x180016e49  xorps   xmm0, xmm0
0x180016e4c  lea     r9, [rsp+0B8h+var_70]
0x180016e51  movups  [rsp+0B8h+var_70], xmm0
0x180016e56  xor     r8d, r8d
0x180016e59  mov     dword ptr [rsp+0B8h+var_70], 20h ; ' '
0x180016e61  mov     rdx, rsi
0x180016e64  mov     rcx, rax
0x180016e67  movups  [rsp+0B8h+var_60], xmm0
0x180016e6c  call    cs:__imp_DevObjOpenDeviceInterface
0x180016e72  test    eax, eax
0x180016e74  jz      loc_180016F5A
0x180016e7a  xorps   xmm0, xmm0
0x180016e7d  movups  [rsp+0B8h+var_50], xmm0
0x180016e82  movups  [rsp+0B8h+var_40], xmm0
0x180016e87  movups  [rsp+0B8h+var_30], xmm0
0x180016e8f  call    cs:__imp_GetProcessHeap
0x180016e95  mov     edx, 8; dwFlags
0x180016e9a  mov     r8d, 210h; dwBytes
0x180016ea0  mov     rcx, rax; hHeap
0x180016ea3  call    cs:__imp_HeapAlloc
0x180016ea9  mov     rdi, rax
0x180016eac  test    rax, rax
0x180016eaf  jnz     short loc_180016EBB
0x180016eb1  mov     edi, 8007000Eh
0x180016eb6  jmp     loc_180016F4C
0x180016ebb  mov     dword ptr [rax], 8
0x180016ec1  lea     rdx, [rsp+0B8h+var_70]
0x180016ec6  lea     rax, [rsp+0B8h+var_50]
0x180016ecb  mov     dword ptr [rsp+0B8h+var_50], 30h ; '0'
0x180016ed3  mov     [rsp+0B8h+var_90], rax
0x180016ed8  mov     r9d, 210h
0x180016ede  mov     r8, rdi
0x180016ee1  mov     [rsp+0B8h+var_98], rbp
0x180016ee6  mov     rcx, rbx
0x180016ee9  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x180016eef  test    eax, eax
0x180016ef1  jz      short loc_180016F36
0x180016ef3  mov     [rsp+0B8h+var_88], rbp
0x180016ef8  lea     rax, [rsp+0B8h+var_78]
0x180016efd  mov     dword ptr [rsp+0B8h+var_90], 4
0x180016f05  lea     rdx, [rsp+0B8h+var_50]
0x180016f0a  xor     r9d, r9d
0x180016f0d  mov     [rsp+0B8h+var_98], rax
0x180016f12  mov     r8d, 22h ; '"'
0x180016f18  mov     [rsp+0B8h+var_78], ebp
0x180016f1c  mov     rcx, rbx
0x180016f1f  call    cs:__imp_DevObjGetDeviceRegistryProperty
0x180016f25  test    eax, eax
0x180016f27  jz      short loc_180016F36
0x180016f29  cmp     [rsp+0B8h+var_78], ebp
0x180016f2d  jnz     short loc_180016F36
0x180016f2f  mov     dword ptr [r14], 1
0x180016f36  call    cs:__imp_GetProcessHeap
0x180016f3c  mov     r8, rdi; lpMem
0x180016f3f  xor     edx, edx; dwFlags
0x180016f41  mov     rcx, rax; hHeap
0x180016f44  call    cs:__imp_HeapFree
0x180016f4a  mov     edi, ebp
0x180016f4c  lea     rdx, [rsp+0B8h+var_70]
0x180016f51  mov     rcx, rbx
0x180016f54  call    cs:__imp_DevObjDeleteDeviceInterfaceData
0x180016f5a  mov     rcx, rbx
0x180016f5d  call    cs:__imp_DevObjDestroyDeviceInfoList
0x180016f63  mov     eax, edi
0x180016f65  mov     rcx, [rsp+0B8h+var_20]
0x180016f6d  xor     rcx, rsp; StackCookie
0x180016f70  call    __security_check_cookie
0x180016f75  lea     r11, [rsp+0B8h+var_18]
0x180016f7d  mov     rbx, [r11+30h]
0x180016f81  mov     rbp, [r11+38h]
0x180016f85  mov     rsp, r11
0x180016f88  pop     r14
0x180016f8a  pop     rdi
0x180016f8b  pop     rsi
0x180016f8c  retn
```
