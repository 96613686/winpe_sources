# CDevNodeCollection::CDevNodeCollection(void)

- ea: `0x1800081a0`
- end: `0x180008201`
- name: `??0CDevNodeCollection@@QEAA@XZ`
- size: `97`
- prototype: `CDevNodeCollection *__fastcall(CDevNodeCollection *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180003cf4`
- `0x18000450c`
- `0x180005314`
- `0x180005a48`
- `0x180005da0`
- `0x1800065f8`

## callees

- `0x180008020`
- `0x1800081a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081e5`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800081cc`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800081cc`

## pseudocode

```c
CDevNodeCollection *__fastcall CDevNodeCollection::CDevNodeCollection(CDevNodeCollection *this)
{
  __int64 DeviceInfoList; // rax
  DWORD LastError; // eax

  *((_QWORD *)this + 1) = 4;
  *((_QWORD *)this + 2) = 0;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  *(_QWORD *)this = DeviceInfoList;
  if ( DeviceInfoList == -1 && GetLastError() )
  {
    LastError = GetLastError();
    CException::ThrowException(LastError, 0, 0);
  }
  return this;
}

```

## disassembly

```asm
0x1800081a0  push    rbx
0x1800081a2  sub     rsp, 30h
0x1800081a6  mov     rbx, rcx
0x1800081a9  mov     qword ptr [rcx+8], 4
0x1800081b1  mov     qword ptr [rcx+10h], 0
0x1800081b9  xor     r9d, r9d
0x1800081bc  xor     ecx, ecx
0x1800081be  mov     [rsp+38h+var_18], 0
0x1800081c7  xor     r8d, r8d
0x1800081ca  xor     edx, edx
0x1800081cc  call    cs:__imp_DevObjCreateDeviceInfoList
0x1800081d2  mov     [rbx], rax
0x1800081d5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800081d9  jnz     short loc_1800081F8
0x1800081db  call    cs:__imp_GetLastError
0x1800081e1  test    eax, eax
0x1800081e3  jz      short loc_1800081F8
0x1800081e5  call    cs:__imp_GetLastError
0x1800081eb  xor     r8d, r8d
0x1800081ee  xor     edx, edx
0x1800081f0  mov     ecx, eax
0x1800081f2  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x1800081f8  mov     rax, rbx
0x1800081fb  add     rsp, 30h
0x1800081ff  pop     rbx
0x180008200  retn
```
