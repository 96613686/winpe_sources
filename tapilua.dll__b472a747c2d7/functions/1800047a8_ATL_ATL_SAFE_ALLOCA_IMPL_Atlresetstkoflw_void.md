# ATL::_ATL_SAFE_ALLOCA_IMPL::_Atlresetstkoflw(void)

- ea: `0x1800047a8`
- end: `0x1800048d7`
- name: `?_Atlresetstkoflw@_ATL_SAFE_ALLOCA_IMPL@ATL@@YAHXZ`
- size: `303`
- prototype: `BOOL __fastcall(ATL::_ATL_SAFE_ALLOCA_IMPL *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004730`

## callees

- `0x180001470`
- `0x1800047a8`

## import_xrefs

- `KERNEL32!VirtualQuery` at `0x18000480e`
- `KERNEL32!VirtualQuery` at `0x180004877`
- `KERNEL32!VirtualQuery` at `0x18000480e`
- `KERNEL32!VirtualQuery` at `0x180004877`
- `KERNEL32!GetSystemInfo` at `0x180004821`
- `KERNEL32!GetSystemInfo` at `0x180004821`
- `KERNEL32!VirtualProtect` at `0x1800048cc`
- `KERNEL32!VirtualProtect` at `0x1800048cc`
- `KERNEL32!VirtualAlloc` at `0x1800048b6`
- `KERNEL32!VirtualAlloc` at `0x1800048b6`

## pseudocode

```c
BOOL __fastcall ATL::_ATL_SAFE_ALLOCA_IMPL::_Atlresetstkoflw(ATL::_ATL_SAFE_ALLOCA_IMPL *this)
{
  char *AllocationBase; // rdi
  SIZE_T dwPageSize; // r14
  PVOID BaseAddress; // rsi
  char *v4; // rbx
  _BYTE Address[16]; // [rsp+10h] [rbp-10h] BYREF
  DWORD flOldProtect; // [rsp+20h] [rbp+0h] BYREF
  _MEMORY_BASIC_INFORMATION Buffer; // [rsp+28h] [rbp+8h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+58h] [rbp+38h] BYREF

  flOldProtect = 0;
  memset(&Buffer, 0, sizeof(Buffer));
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  if ( VirtualQuery(Address, &Buffer, 0x30u) )
  {
    AllocationBase = (char *)Buffer.AllocationBase;
    GetSystemInfo(&SystemInfo);
    dwPageSize = SystemInfo.dwPageSize;
    BaseAddress = AllocationBase + 0x2000;
    v4 = (char *)(((unsigned __int64)Address & ~(unsigned __int64)(SystemInfo.dwPageSize - 1)) - SystemInfo.dwPageSize);
    if ( v4 >= AllocationBase + 0x2000 )
    {
      while ( VirtualQuery(AllocationBase, &Buffer, 0x30u) )
      {
        if ( (Buffer.State & 0x1000) != 0 )
        {
          if ( (Buffer.Protect & 0x100) != 0 )
            return 1;
          if ( v4 >= Buffer.BaseAddress )
          {
            if ( Buffer.BaseAddress >= BaseAddress )
              BaseAddress = Buffer.BaseAddress;
            VirtualAlloc(BaseAddress, dwPageSize, 0x1000u, 4u);
            return VirtualProtect(BaseAddress, dwPageSize, 0x104u, &flOldProtect);
          }
          return 0;
        }
        AllocationBase += Buffer.RegionSize;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800047a8  push    rbp
0x1800047aa  push    rbx
0x1800047ab  push    rsi
0x1800047ac  push    rdi
0x1800047ad  push    r14
0x1800047af  push    r15
0x1800047b1  sub     rsp, 98h
0x1800047b8  lea     rbp, [rsp+20h]
0x1800047bd  mov     rax, cs:__security_cookie
0x1800047c4  xor     rax, rbp
0x1800047c7  mov     [rbp+0A0h+var_38], rax
0x1800047cb  mov     eax, [rsp+0C0h+var_C0]
0x1800047ce  xorps   xmm0, xmm0
0x1800047d1  xorps   xmm1, xmm1
0x1800047d4  mov     [rbp+0A0h+flOldProtect], 0
0x1800047db  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x1800047df  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x1800047e3  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x1800047e7  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x1800047eb  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x1800047ef  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x1800047f3  sub     rsp, 10h
0x1800047f7  lea     rsi, [rsp+0D0h+Address]
0x1800047fc  mov     eax, [rsi]
0x1800047fe  mov     r15d, 30h ; '0'
0x180004804  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x180004808  mov     r8d, r15d; dwLength
0x18000480b  mov     rcx, rsi; lpAddress
0x18000480e  call    cs:__imp_VirtualQuery
0x180004814  test    rax, rax
0x180004817  jz      short loc_180004845
0x180004819  mov     rdi, [rbp+0A0h+Buffer.AllocationBase]
0x18000481d  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x180004821  call    cs:__imp_GetSystemInfo
0x180004827  mov     eax, [rbp+0A0h+SystemInfo.dwPageSize]
0x18000482a  mov     r14d, eax
0x18000482d  lea     ebx, [rax-1]
0x180004830  not     rbx
0x180004833  and     rbx, rsi
0x180004836  lea     rsi, [rdi+2000h]
0x18000483d  sub     rbx, rax
0x180004840  cmp     rbx, rsi
0x180004843  jnb     short loc_18000486D
0x180004845  xor     eax, eax
0x180004847  mov     rcx, [rbp+0A0h+var_38]
0x18000484b  xor     rcx, rbp; StackCookie
0x18000484e  call    __security_check_cookie
0x180004853  lea     rsp, [rbp+78h]
0x180004857  pop     r15
0x180004859  pop     r14
0x18000485b  pop     rdi
0x18000485c  pop     rsi
0x18000485d  pop     rbx
0x18000485e  pop     rbp
0x18000485f  retn
0x180004860  test    [rbp+0A0h+Buffer.State], 1000h
0x180004867  jnz     short loc_180004884
0x180004869  add     rdi, [rbp+0A0h+Buffer.RegionSize]
0x18000486d  mov     r8, r15; dwLength
0x180004870  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x180004874  mov     rcx, rdi; lpAddress
0x180004877  call    cs:__imp_VirtualQuery
0x18000487d  test    rax, rax
0x180004880  jnz     short loc_180004860
0x180004882  jmp     short loc_180004845
0x180004884  test    [rbp+0A0h+Buffer.Protect], 100h
0x18000488b  jz      short loc_180004894
0x18000488d  mov     eax, 1
0x180004892  jmp     short loc_180004847
0x180004894  mov     rax, [rbp+0A0h+Buffer.BaseAddress]
0x180004898  cmp     rbx, rax
0x18000489b  jb      short loc_180004845
0x18000489d  cmp     rax, rsi
0x1800048a0  mov     r9d, 4; flProtect
0x1800048a6  mov     r8d, 1000h; flAllocationType
0x1800048ac  mov     rdx, r14; dwSize
0x1800048af  cmovnb  rsi, rax
0x1800048b3  mov     rcx, rsi; lpAddress
0x1800048b6  call    cs:__imp_VirtualAlloc
0x1800048bc  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x1800048c0  mov     r8d, 104h; flNewProtect
0x1800048c6  mov     rdx, r14; dwSize
0x1800048c9  mov     rcx, rsi; lpAddress
0x1800048cc  call    cs:__imp_VirtualProtect
0x1800048d2  jmp     loc_180004847
```
