# IsCacheUVCControlEnabled

- ea: `0x14000e8a8`
- end: `0x14000e95c`
- name: `IsCacheUVCControlEnabled`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14001bdfc`

## callees

- `0x14000e8a8`
- `0x14000e964`
- `0x14001ab4c`
- `0x14001b15c`

## string_xrefs

- `0x14000e8f8`: `CacheUVCControl`

## pseudocode

```c
__int64 __fastcall IsCacheUVCControlEnabled(__int64 a1)
{
  __int64 v1; // rbx
  __int64 result; // rax
  int v3; // [rsp+40h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 16);
  v3 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids, v1);
  result = GetDeviceRegValueDword(*(struct _DEVICE_OBJECT **)(*(_QWORD *)(v1 + 24) + 32LL), 1u, L"CacheUVCControl", &v3);
  if ( (int)result >= 0 )
  {
    result = v3 != 0;
    *(_DWORD *)(v1 + 1424) = result;
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    return WPP_SF_qD(
             WPP_GLOBAL_Control->AttachedDevice,
             82,
             WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids,
             v1,
             result);
  }
  return result;
}

```

## disassembly

```asm
0x14000e8a8  mov     [rsp+arg_8], rbx
0x14000e8ad  push    rdi
0x14000e8ae  sub     rsp, 30h
0x14000e8b2  mov     rbx, [rcx+10h]
0x14000e8b6  mov     [rsp+38h+arg_0], 0
0x14000e8be  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e8c5  lea     rdi, WPP_GLOBAL_Control
0x14000e8cc  cmp     rcx, rdi
0x14000e8cf  jz      short loc_14000E8EF
0x14000e8d1  cmp     byte ptr [rcx+29h], 4
0x14000e8d5  jb      short loc_14000E8EF
0x14000e8d7  mov     rcx, [rcx+18h]
0x14000e8db  lea     r8, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids
0x14000e8e2  mov     edx, 51h ; 'Q'
0x14000e8e7  mov     r9, rbx
0x14000e8ea  call    WPP_SF_q
0x14000e8ef  mov     rcx, [rbx+18h]
0x14000e8f3  lea     r9, [rsp+38h+arg_0]
0x14000e8f8  lea     r8, aCacheuvccontro; "CacheUVCControl"
0x14000e8ff  mov     edx, 1
0x14000e904  mov     rcx, [rcx+20h]
0x14000e908  call    GetDeviceRegValueDword
0x14000e90d  test    eax, eax
0x14000e90f  jns     short loc_14000E941
0x14000e911  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e918  cmp     rcx, rdi
0x14000e91b  jz      short loc_14000E950
0x14000e91d  cmp     byte ptr [rcx+29h], 2
0x14000e921  jb      short loc_14000E950
0x14000e923  mov     rcx, [rcx+18h]
0x14000e927  lea     r8, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids
0x14000e92e  mov     edx, 52h ; 'R'
0x14000e933  mov     [rsp+38h+var_18], eax
0x14000e937  mov     r9, rbx
0x14000e93a  call    WPP_SF_qD
0x14000e93f  jmp     short loc_14000E950
0x14000e941  xor     eax, eax
0x14000e943  cmp     [rsp+38h+arg_0], eax
0x14000e947  setnz   al
0x14000e94a  mov     [rbx+590h], eax
0x14000e950  mov     rbx, [rsp+38h+arg_8]
0x14000e955  add     rsp, 30h
0x14000e959  pop     rdi
0x14000e95a  retn
```
