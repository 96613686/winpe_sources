# SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)

- ea: `0x180026440`
- end: `0x1800265ee`
- name: `?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z`
- size: `430`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, int, void **, unsigned int *)`
- caller_count: `8`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009890`
- `0x18000b3b0`
- `0x18002fdac`
- `0x180034d38`
- `0x180037e20`
- `0x18003f778`
- `0x1800422a0`
- `0x1800b76c4`

## callees

- `0x180026440`
- `0x180054130`
- `0x18005a1b6`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026595`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026595`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026499`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026499`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800264e8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002655d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800264e8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002655d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026509`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026509`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026579`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026579`

## pseudocode

```c
__int64 __fastcall SHRegAllocData(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        void **a5)
{
  int v6; // edi
  LSTATUS v7; // ebx
  LSTATUS ValueW; // eax
  void *pvData; // rax
  DWORD pcbData; // [rsp+40h] [rbp-138h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-130h] BYREF
  _BYTE Src[256]; // [rsp+50h] [rbp-128h] BYREF

  hkey = a1;
  if ( a2 && *a2 )
  {
    v6 = 1;
    v7 = RegOpenKeyExW(a1, a2, 0, 1u, &hkey);
    if ( v7 )
    {
LABEL_18:
      *a5 = 0;
      goto LABEL_19;
    }
    a1 = hkey;
  }
  else
  {
    v6 = 0;
  }
  pcbData = 256;
  ValueW = RegGetValueW(a1, 0, a3, 2u, 0, Src, &pcbData);
  v7 = ValueW;
  if ( !ValueW || ValueW == 234 )
  {
    pvData = CoTaskMemAlloc(pcbData);
    *a5 = pvData;
    if ( pvData )
    {
      if ( v7 )
      {
        if ( RegGetValueW(hkey, 0, a3, 2u, 0, pvData, &pcbData) )
        {
          v7 = 1003;
          CoTaskMemFree(*a5);
        }
        else
        {
          v7 = 0;
        }
      }
      else
      {
        memcpy_0(pvData, Src, pcbData);
      }
    }
    else
    {
      v7 = 14;
    }
  }
  if ( v6 )
    RegCloseKey(hkey);
  if ( v7 )
    goto LABEL_18;
LABEL_19:
  if ( v7 > 0 )
    return (unsigned __int16)v7 | 0x80070000;
  else
    return (unsigned int)v7;
}

```

## disassembly

```asm
0x180026440  mov     r11, rsp
0x180026443  push    rbx
0x180026444  sub     rsp, 170h
0x18002644b  mov     rax, cs:__security_cookie
0x180026452  xor     rax, rsp
0x180026455  mov     [rsp+178h+var_28], rax
0x18002645d  mov     [r11+20h], rsi
0x180026461  mov     rsi, r8
0x180026464  mov     [r11-10h], rdi
0x180026468  mov     [r11-18h], r14
0x18002646c  mov     r14, [rsp+178h+arg_20]
0x180026474  mov     [rsp+178h+hkey], rcx
0x180026479  test    rdx, rdx
0x18002647c  jz      short loc_1800264B6
0x18002647e  cmp     word ptr [rdx], 0
0x180026482  jz      short loc_1800264B6
0x180026484  lea     rax, [rsp+178h+hkey]
0x180026489  mov     edi, 1
0x18002648e  mov     r9d, edi; samDesired
0x180026491  mov     [rsp+178h+phkResult], rax; phkResult
0x180026496  xor     r8d, r8d; ulOptions
0x180026499  call    cs:__imp_RegOpenKeyExW
0x1800264a0  nop     dword ptr [rax+rax+00h]
0x1800264a5  mov     ebx, eax
0x1800264a7  test    eax, eax
0x1800264a9  jnz     loc_1800265A5
0x1800264af  mov     rcx, [rsp+178h+hkey]; hkey
0x1800264b4  jmp     short loc_1800264B8
0x1800264b6  xor     edi, edi
0x1800264b8  lea     rax, [rsp+178h+var_138]
0x1800264bd  mov     [rsp+178h+var_138], 100h
0x1800264c5  mov     [rsp+178h+pcbData], rax; pcbData
0x1800264ca  mov     r9d, 2; dwFlags
0x1800264d0  lea     rax, [rsp+178h+Src]
0x1800264d5  mov     r8, rsi; lpValue
0x1800264d8  mov     [rsp+178h+pvData], rax; pvData
0x1800264dd  xor     edx, edx; lpSubKey
0x1800264df  mov     [rsp+178h+phkResult], 0; pdwType
0x1800264e8  call    cs:__imp_RegGetValueW
0x1800264ef  nop     dword ptr [rax+rax+00h]
0x1800264f4  mov     ebx, eax
0x1800264f6  test    eax, eax
0x1800264f8  jz      short loc_180026505
0x1800264fa  cmp     eax, 0EAh
0x1800264ff  jnz     loc_18002658C
0x180026505  mov     ecx, [rsp+178h+var_138]; cb
0x180026509  call    cs:__imp_CoTaskMemAlloc
0x180026510  nop     dword ptr [rax+rax+00h]
0x180026515  mov     [r14], rax
0x180026518  test    rax, rax
0x18002651b  jz      short loc_180026587
0x18002651d  test    ebx, ebx
0x18002651f  jnz     short loc_180026535
0x180026521  mov     r8d, [rsp+178h+var_138]; Size
0x180026526  lea     rdx, [rsp+178h+Src]; Src
0x18002652b  mov     rcx, rax; void *
0x18002652e  call    memcpy_0
0x180026533  jmp     short loc_18002658C
0x180026535  lea     rcx, [rsp+178h+var_138]
0x18002653a  mov     r9d, 2; dwFlags
0x180026540  mov     [rsp+178h+pcbData], rcx; pcbData
0x180026545  mov     r8, rsi; lpValue
0x180026548  mov     rcx, [rsp+178h+hkey]; hkey
0x18002654d  xor     edx, edx; lpSubKey
0x18002654f  mov     [rsp+178h+pvData], rax; pvData
0x180026554  mov     [rsp+178h+phkResult], 0; pdwType
0x18002655d  call    cs:__imp_RegGetValueW
0x180026564  nop     dword ptr [rax+rax+00h]
0x180026569  test    eax, eax
0x18002656b  jnz     short loc_180026571
0x18002656d  xor     ebx, ebx
0x18002656f  jmp     short loc_18002658C
0x180026571  mov     rcx, [r14]; pv
0x180026574  mov     ebx, 3EBh
0x180026579  call    cs:__imp_CoTaskMemFree
0x180026580  nop     dword ptr [rax+rax+00h]
0x180026585  jmp     short loc_18002658C
0x180026587  mov     ebx, 0Eh
0x18002658c  test    edi, edi
0x18002658e  jz      short loc_1800265A1
0x180026590  mov     rcx, [rsp+178h+hkey]; hKey
0x180026595  call    cs:__imp_RegCloseKey
0x18002659c  nop     dword ptr [rax+rax+00h]
0x1800265a1  test    ebx, ebx
0x1800265a3  jz      short loc_1800265AC
0x1800265a5  mov     qword ptr [r14], 0
0x1800265ac  mov     r14, [rsp+178h+var_18]
0x1800265b4  mov     rdi, [rsp+178h+var_10]
0x1800265bc  mov     rsi, [rsp+178h+arg_18]
0x1800265c4  test    ebx, ebx
0x1800265c6  jg      short loc_1800265CC
0x1800265c8  mov     eax, ebx
0x1800265ca  jmp     short loc_1800265D4
0x1800265cc  movzx   eax, bx
0x1800265cf  or      eax, 80070000h
0x1800265d4  mov     rcx, [rsp+178h+var_28]
0x1800265dc  xor     rcx, rsp; StackCookie
0x1800265df  call    __security_check_cookie
0x1800265e4  add     rsp, 170h
0x1800265eb  pop     rbx
0x1800265ec  retn
```
