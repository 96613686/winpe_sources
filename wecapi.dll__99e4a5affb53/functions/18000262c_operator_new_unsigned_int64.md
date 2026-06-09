# operator new(unsigned __int64)

- ea: `0x18000262c`
- end: `0x1800026b9`
- name: `??2@YAPEAX_K@Z`
- size: `141`
- prototype: `void *__fastcall(SIZE_T dwBytes)`
- caller_count: `21`
- callee_count: `4`
- tags: ``

## callers

- `0x1800010a0`
- `0x180001f2c`
- `0x180003604`
- `0x180003c0c`
- `0x180003c4c`
- `0x180003d78`
- `0x180005220`
- `0x1800054c0`
- `0x1800066c4`
- `0x180006fb8`
- `0x180007720`
- `0x180009ba0`
- `0x180009cb8`
- `0x180009d3c`
- `0x180009de0`
- `0x18000a72c`
- `0x18000aa3c`
- `0x18000ad88`
- `0x18000b6b8`
- `0x18000be11`
- `0x18000c607`

## callees

- `0x180001aac`
- `0x1800025d0`
- `0x18000262c`
- `0x1800027ac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002635`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002635`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002643`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002643`

## pseudocode

```c
LPVOID __fastcall operator new(SIZE_T dwBytes)
{
  HANDLE ProcessHeap; // rax
  LPVOID result; // rax
  _BYTE pExceptionObject[72]; // [rsp+20h] [rbp-48h] BYREF

  ProcessHeap = GetProcessHeap();
  result = HeapAlloc(ProcessHeap, 0, dwBytes);
  if ( !result )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_41100dd4e1ff3f44031d028098cfc1f2_Traceguids, 14);
    }
    wmi::GenericException::GenericException(
      (wmi::GenericException *)pExceptionObject,
      0xEu,
      "admin\\wmi\\events\\forwarding\\collector\\api\\localloc.cpp",
      13);
    throw (wmi::GenericException *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x18000262c  push    rbx
0x18000262e  sub     rsp, 60h
0x180002632  mov     rbx, rcx
0x180002635  call    cs:__imp_GetProcessHeap
0x18000263b  mov     r8, rbx; dwBytes
0x18000263e  xor     edx, edx; dwFlags
0x180002640  mov     rcx, rax; hHeap
0x180002643  call    cs:__imp_HeapAlloc
0x180002649  test    rax, rax
0x18000264c  jz      short loc_180002654
0x18000264e  add     rsp, 60h
0x180002652  pop     rbx
0x180002653  retn
0x180002654  mov     rcx, cs:WPP_GLOBAL_Control
0x18000265b  lea     rax, WPP_GLOBAL_Control
0x180002662  mov     ebx, 0Eh
0x180002667  cmp     rcx, rax
0x18000266a  jz      short loc_18000268E
0x18000266c  test    byte ptr [rcx+1Ch], 1
0x180002670  jz      short loc_18000268E
0x180002672  cmp     byte ptr [rcx+19h], 2
0x180002676  jb      short loc_18000268E
0x180002678  mov     rcx, [rcx+10h]
0x18000267c  lea     edx, [rbx-4]
0x18000267f  mov     r9d, ebx
0x180002682  lea     r8, WPP_41100dd4e1ff3f44031d028098cfc1f2_Traceguids
0x180002689  call    WPP_SF_D
0x18000268e  mov     r9d, 0Dh; int
0x180002694  lea     r8, aAdminWmiEvents_2; "admin\\wmi\\events\\forwarding\\collect"...
0x18000269b  mov     edx, ebx; unsigned int
0x18000269d  lea     rcx, [rsp+68h+pExceptionObject]; this
0x1800026a2  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x1800026a7  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800026ae  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800026b3  call    _CxxThrowException_0
```
