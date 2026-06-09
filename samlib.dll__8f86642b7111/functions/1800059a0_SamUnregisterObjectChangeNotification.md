# SamUnregisterObjectChangeNotification

- ea: `0x1800059a0`
- end: `0x180005aa8`
- name: `SamUnregisterObjectChangeNotification`
- size: `264`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x1800059a0`
- `0x180006060`
- `0x180006620`
- `0x1800078c0`
- `0x18000807c`
- `0x180014558`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005a08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005a08`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005a2c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005a2c`

## pseudocode

```c
__int64 __fastcall SamUnregisterObjectChangeNotification(unsigned int a1, __int64 a2, __int64 a3)
{
  int v5; // ebx
  HLOCAL hMem; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v8[2]; // [rsp+38h] [rbp-30h] BYREF
  unsigned int v9; // [rsp+48h] [rbp-20h]
  DWORD CurrentProcessId; // [rsp+4Ch] [rbp-1Ch]

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_Lq(*((_QWORD *)WPP_GLOBAL_Control + 2), 368, a3, a1, a2);
  v8[0] = 0;
  v8[1] = a2;
  v9 = a1;
  hMem = 0;
  CurrentProcessId = GetCurrentProcessId();
  v5 = SamPerformGenericOperation(0, 0, v8, &hMem);
  LocalFree(hMem);
  if ( v5 < 0 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        370,
        &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids,
        (unsigned int)v5);
  }
  else if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 369, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800059a0  mov     [rsp+arg_10], rbx
0x1800059a5  push    rdi
0x1800059a6  sub     rsp, 60h
0x1800059aa  mov     rax, cs:__security_cookie
0x1800059b1  xor     rax, rsp
0x1800059b4  mov     [rsp+68h+var_18], rax
0x1800059b9  mov     rdi, rdx
0x1800059bc  mov     ebx, ecx
0x1800059be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059c5  test    byte ptr [rcx+1Ch], 2
0x1800059c9  jz      short loc_1800059E7
0x1800059cb  cmp     byte ptr [rcx+19h], 4
0x1800059cf  jb      short loc_1800059E7
0x1800059d1  mov     rcx, [rcx+10h]
0x1800059d5  mov     edx, 170h
0x1800059da  mov     r9d, ebx
0x1800059dd  mov     [rsp+68h+var_48], rdi
0x1800059e2  call    WPP_SF_Lq
0x1800059e7  xor     eax, eax
0x1800059e9  xorps   xmm0, xmm0
0x1800059ec  movups  [rsp+68h+var_30], xmm0
0x1800059f1  mov     [rsp+68h+var_20], rax
0x1800059f6  mov     qword ptr [rsp+68h+var_30+8], rdi
0x1800059fb  mov     byte ptr [rsp+68h+var_30], al
0x1800059ff  mov     dword ptr [rsp+68h+var_20], ebx
0x180005a03  mov     [rsp+68h+hMem], rax
0x180005a08  call    cs:__imp_GetCurrentProcessId
0x180005a0e  lea     r9, [rsp+68h+hMem]
0x180005a13  xor     edx, edx
0x180005a15  lea     r8, [rsp+68h+var_30]
0x180005a1a  mov     dword ptr [rsp+68h+var_20+4], eax
0x180005a1e  xor     ecx, ecx
0x180005a20  call    SamPerformGenericOperation
0x180005a25  mov     rcx, [rsp+68h+hMem]; hMem
0x180005a2a  mov     ebx, eax
0x180005a2c  call    cs:__imp_LocalFree
0x180005a32  test    ebx, ebx
0x180005a34  js      short loc_180005A60
0x180005a36  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a3d  test    byte ptr [rcx+1Ch], 2
0x180005a41  jz      short loc_180005A8B
0x180005a43  cmp     byte ptr [rcx+19h], 4
0x180005a47  jb      short loc_180005A8B
0x180005a49  mov     rcx, [rcx+10h]
0x180005a4d  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180005a54  mov     edx, 171h
0x180005a59  call    WPP_SF_
0x180005a5e  jmp     short loc_180005A8B
0x180005a60  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a67  test    byte ptr [rcx+1Ch], 2
0x180005a6b  jz      short loc_180005A8B
0x180005a6d  cmp     byte ptr [rcx+19h], 2
0x180005a71  jb      short loc_180005A8B
0x180005a73  mov     rcx, [rcx+10h]
0x180005a77  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180005a7e  mov     edx, 172h
0x180005a83  mov     r9d, ebx
0x180005a86  call    WPP_SF_D
0x180005a8b  mov     eax, ebx
0x180005a8d  mov     rcx, [rsp+68h+var_18]
0x180005a92  xor     rcx, rsp; StackCookie
0x180005a95  call    __security_check_cookie
0x180005a9a  mov     rbx, [rsp+68h+arg_10]
0x180005aa2  add     rsp, 60h
0x180005aa6  pop     rdi
0x180005aa7  retn
```
