# FindFirstDisk(ulong,ushort *)

- ea: `0x18002a530`
- end: `0x18002a5f1`
- name: `?FindFirstDisk@@YAPEAXKPEAG@Z`
- size: `193`
- prototype: `void *(unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180020df0`

## callees

- `0x180021044`
- `0x18002a530`
- `0x18002a5f8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a551`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a551`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a562`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a562`
- `DEVOBJ!DevObjGetClassDevs` at `0x18002a5b8`
- `DEVOBJ!DevObjGetClassDevs` at `0x18002a5b8`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18002a588`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18002a588`

## pseudocode

```c
GUID *__fastcall FindFirstDisk(__int64 a1, unsigned __int16 *a2)
{
  __int64 v2; // rdi
  GUID *v4; // rax
  GUID *v5; // rbx
  __int64 DeviceInfoList; // rax
  unsigned int v7; // edx

  v2 = -1;
  *a2 = 0;
  v4 = (GUID *)LocalAlloc(0x40u, 0x20u);
  v5 = v4;
  if ( v4 )
  {
    *v4 = GUID_DEVINTERFACE_DISK;
    DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
    *(_QWORD *)&v5[1].Data1 = DeviceInfoList;
    if ( DeviceInfoList != -1
      && (unsigned int)DevObjGetClassDevs(DeviceInfoList, v5, 0, 18, 0, 0)
      && FindNextDisk(v5, v7, a2) )
    {
      return v5;
    }
    else
    {
      FindDiskClose(v5);
    }
  }
  else
  {
    SetLastError(8u);
  }
  return (GUID *)v2;
}

```

## disassembly

```asm
0x18002a530  mov     [rsp+arg_0], rbx
0x18002a535  mov     [rsp+arg_8], rsi
0x18002a53a  push    rdi
0x18002a53b  sub     rsp, 30h
0x18002a53f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002a543  xor     eax, eax
0x18002a545  mov     rsi, rdx
0x18002a548  mov     [rdx], ax
0x18002a54b  lea     edx, [rdi+21h]; uBytes
0x18002a54e  lea     ecx, [rdi+41h]; uFlags
0x18002a551  call    cs:__imp_LocalAlloc
0x18002a557  mov     rbx, rax
0x18002a55a  test    rax, rax
0x18002a55d  jnz     short loc_18002A56A
0x18002a55f  lea     ecx, [rdi+9]; dwErrCode
0x18002a562  call    cs:__imp_SetLastError
0x18002a568  jmp     short loc_18002A5DE
0x18002a56a  movups  xmm0, xmmword ptr cs:GUID_DEVINTERFACE_DISK.Data1
0x18002a571  xor     r9d, r9d
0x18002a574  mov     [rsp+38h+var_18], 0
0x18002a57d  xor     r8d, r8d
0x18002a580  xor     edx, edx
0x18002a582  xor     ecx, ecx
0x18002a584  movdqu  xmmword ptr [rax], xmm0
0x18002a588  call    cs:__imp_DevObjCreateDeviceInfoList
0x18002a58e  mov     [rbx+10h], rax
0x18002a592  cmp     rax, rdi
0x18002a595  jz      short loc_18002A5D6
0x18002a597  mov     [rsp+38h+var_10], 0
0x18002a5a0  mov     r9d, 12h
0x18002a5a6  xor     r8d, r8d
0x18002a5a9  mov     [rsp+38h+var_18], 0
0x18002a5b2  mov     rdx, rbx
0x18002a5b5  mov     rcx, rax
0x18002a5b8  call    cs:__imp_DevObjGetClassDevs
0x18002a5be  test    eax, eax
0x18002a5c0  jz      short loc_18002A5D6
0x18002a5c2  mov     r8, rsi; unsigned __int16 *
0x18002a5c5  mov     rcx, rbx; void *
0x18002a5c8  call    ?FindNextDisk@@YAHPEAXKPEAG@Z; FindNextDisk(void *,ulong,ushort *)
0x18002a5cd  test    eax, eax
0x18002a5cf  jz      short loc_18002A5D6
0x18002a5d1  mov     rdi, rbx
0x18002a5d4  jmp     short loc_18002A5DE
0x18002a5d6  mov     rcx, rbx; void *
0x18002a5d9  call    ?FindDiskClose@@YAXPEAX@Z; FindDiskClose(void *)
0x18002a5de  mov     rbx, [rsp+38h+arg_0]
0x18002a5e3  mov     rax, rdi
0x18002a5e6  mov     rsi, [rsp+38h+arg_8]
0x18002a5eb  add     rsp, 30h
0x18002a5ef  pop     rdi
0x18002a5f0  retn
```
