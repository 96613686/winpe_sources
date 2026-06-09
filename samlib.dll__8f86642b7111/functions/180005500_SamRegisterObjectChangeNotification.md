# SamRegisterObjectChangeNotification

- ea: `0x180005500`
- end: `0x18000561b`
- name: `SamRegisterObjectChangeNotification`
- size: `283`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x180005500`
- `0x180006060`
- `0x180006620`
- `0x1800078c0`
- `0x18000807c`
- `0x180014558`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005551`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005551`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005575`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005575`

## pseudocode

```c
__int64 __fastcall SamRegisterObjectChangeNotification(unsigned int a1, __int64 a2, __int64 a3)
{
  int v5; // ebx
  HLOCAL hMem; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v8[2]; // [rsp+38h] [rbp-30h] BYREF
  unsigned int v9; // [rsp+48h] [rbp-20h]
  DWORD CurrentProcessId; // [rsp+4Ch] [rbp-1Ch]

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_Lq(*((_QWORD *)WPP_GLOBAL_Control + 2), 365, a3, a1, a2);
  v8[0] = 1;
  v8[1] = a2;
  v9 = a1;
  hMem = 0;
  CurrentProcessId = GetCurrentProcessId();
  v5 = SamPerformGenericOperation(0, 0, v8, &hMem);
  LocalFree(hMem);
  if ( v5 >= 0 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 366, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids);
  }
  else if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      367,
      &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids,
      (unsigned int)v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180005500  mov     [rsp+arg_10], rbx
0x180005505  push    rdi
0x180005506  sub     rsp, 60h
0x18000550a  mov     rax, cs:__security_cookie
0x180005511  xor     rax, rsp
0x180005514  mov     [rsp+68h+var_18], rax
0x180005519  mov     rdi, rdx
0x18000551c  mov     ebx, ecx
0x18000551e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005525  test    byte ptr [rcx+1Ch], 2
0x180005529  jnz     loc_1800055D3
0x18000552f  xor     eax, eax
0x180005531  xorps   xmm0, xmm0
0x180005534  movups  [rsp+68h+var_30], xmm0
0x180005539  mov     [rsp+68h+var_20], rax
0x18000553e  mov     qword ptr [rsp+68h+var_30+8], rdi
0x180005543  mov     byte ptr [rsp+68h+var_30], 1
0x180005548  mov     dword ptr [rsp+68h+var_20], ebx
0x18000554c  mov     [rsp+68h+hMem], rax
0x180005551  call    cs:__imp_GetCurrentProcessId
0x180005557  lea     r9, [rsp+68h+hMem]
0x18000555c  xor     edx, edx
0x18000555e  lea     r8, [rsp+68h+var_30]
0x180005563  mov     dword ptr [rsp+68h+var_20+4], eax
0x180005567  xor     ecx, ecx
0x180005569  call    SamPerformGenericOperation
0x18000556e  mov     rcx, [rsp+68h+hMem]; hMem
0x180005573  mov     ebx, eax
0x180005575  call    cs:__imp_LocalFree
0x18000557b  test    ebx, ebx
0x18000557d  jns     short loc_1800055A9
0x18000557f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005586  test    byte ptr [rcx+1Ch], 2
0x18000558a  jnz     short loc_1800055F8
0x18000558c  mov     eax, ebx
0x18000558e  mov     rcx, [rsp+68h+var_18]
0x180005593  xor     rcx, rsp; StackCookie
0x180005596  call    __security_check_cookie
0x18000559b  mov     rbx, [rsp+68h+arg_10]
0x1800055a3  add     rsp, 60h
0x1800055a7  pop     rdi
0x1800055a8  retn
0x1800055a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055b0  test    byte ptr [rcx+1Ch], 2
0x1800055b4  jz      short loc_18000558C
0x1800055b6  cmp     byte ptr [rcx+19h], 4
0x1800055ba  jb      short loc_18000558C
0x1800055bc  mov     rcx, [rcx+10h]
0x1800055c0  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x1800055c7  mov     edx, 16Eh
0x1800055cc  call    WPP_SF_
0x1800055d1  jmp     short loc_18000558C
0x1800055d3  cmp     byte ptr [rcx+19h], 4
0x1800055d7  jb      loc_18000552F
0x1800055dd  mov     rcx, [rcx+10h]
0x1800055e1  mov     edx, 16Dh
0x1800055e6  mov     r9d, ebx
0x1800055e9  mov     [rsp+68h+var_48], rdi
0x1800055ee  call    WPP_SF_Lq
0x1800055f3  jmp     loc_18000552F
0x1800055f8  cmp     byte ptr [rcx+19h], 2
0x1800055fc  jb      short loc_18000558C
0x1800055fe  mov     rcx, [rcx+10h]
0x180005602  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180005609  mov     edx, 16Fh
0x18000560e  mov     r9d, ebx
0x180005611  call    WPP_SF_D
0x180005616  jmp     loc_18000558C
```
