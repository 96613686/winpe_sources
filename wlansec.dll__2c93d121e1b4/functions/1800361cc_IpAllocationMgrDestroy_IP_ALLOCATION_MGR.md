# IpAllocationMgrDestroy(_IP_ALLOCATION_MGR *)

- ea: `0x1800361cc`
- end: `0x1800362ec`
- name: `?IpAllocationMgrDestroy@@YAKPEAU_IP_ALLOCATION_MGR@@@Z`
- size: `288`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180005bf0`
- `0x1800184ec`
- `0x180035ed0`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000e620`
- `0x1800361cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003628f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003628f`

## pseudocode

```c
__int64 __fastcall IpAllocationMgrDestroy(LPCRITICAL_SECTION lpCriticalSection)
{
  PVOID *v2; // rcx
  unsigned int v3; // ebx
  LONG *p_LockCount; // rbx
  LPCRITICAL_SECTION *v5; // rax
  LPCRITICAL_SECTION v6; // rcx
  LPCRITICAL_SECTION v8; // [rsp+30h] [rbp+8h] BYREF
  LPCRITICAL_SECTION *v9; // [rsp+38h] [rbp+10h] BYREF

  v8 = lpCriticalSection;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 24, &WPP_622467b8f14e3d8e631d784b31d192ed_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( lpCriticalSection )
  {
    do
    {
      p_LockCount = &lpCriticalSection[1].LockCount;
      v5 = *(LPCRITICAL_SECTION **)&lpCriticalSection[1].LockCount;
      if ( v5[1] != (LPCRITICAL_SECTION)&lpCriticalSection[1].LockCount
        || (v6 = *v5, *(LPCRITICAL_SECTION **)&(*v5)->LockCount != v5) )
      {
        __fastfail(3u);
      }
      *(_QWORD *)p_LockCount = v6;
      *(_QWORD *)&v6->LockCount = p_LockCount;
      v9 = v5;
      if ( v5 == (LPCRITICAL_SECTION *)p_LockCount )
        break;
      FreeMSMSecMemory(&v9);
    }
    while ( v9 != (LPCRITICAL_SECTION *)p_LockCount );
    v3 = 0;
    DeleteCriticalSection(lpCriticalSection);
    FreeMSMSecMemory(&v8);
    goto LABEL_13;
  }
  v3 = 87;
  if ( v2 == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)v2 + 68) & 1) != 0 )
  {
    WPP_SF_(v2[7], 25, &WPP_622467b8f14e3d8e631d784b31d192ed_Traceguids);
LABEL_13:
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_DWORD *)v2 + 17) & 0x100) != 0 )
    WPP_SF_d(v2[7], 26, &WPP_622467b8f14e3d8e631d784b31d192ed_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x1800361cc  mov     [rsp+arg_10], rbx
0x1800361d1  mov     [rsp+arg_18], rsi
0x1800361d6  mov     [rsp+arg_0], rcx
0x1800361db  push    rdi
0x1800361dc  sub     rsp, 20h
0x1800361e0  mov     rdi, rcx
0x1800361e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800361ea  lea     rsi, WPP_GLOBAL_Control
0x1800361f1  cmp     rcx, rsi
0x1800361f4  jz      short loc_18003621B
0x1800361f6  test    dword ptr [rcx+44h], 100h
0x1800361fd  jz      short loc_18003621B
0x1800361ff  mov     rcx, [rcx+38h]
0x180036203  lea     r8, WPP_622467b8f14e3d8e631d784b31d192ed_Traceguids
0x18003620a  mov     edx, 18h
0x18003620f  call    WPP_SF_
0x180036214  mov     rcx, cs:WPP_GLOBAL_Control
0x18003621b  test    rdi, rdi
0x18003621e  jnz     short loc_180036247
0x180036220  lea     ebx, [rdi+57h]
0x180036223  cmp     rcx, rsi
0x180036226  jz      loc_1800362D2
0x18003622c  test    byte ptr [rcx+44h], 1
0x180036230  jz      short loc_1800362AC
0x180036232  mov     rcx, [rcx+38h]
0x180036236  lea     edx, [rdi+19h]
0x180036239  lea     r8, WPP_622467b8f14e3d8e631d784b31d192ed_Traceguids
0x180036240  call    WPP_SF_
0x180036245  jmp     short loc_1800362A5
0x180036247  lea     rbx, [rdi+30h]
0x18003624b  mov     rax, [rbx]
0x18003624e  cmp     [rax+8], rbx
0x180036252  jnz     loc_1800362E5
0x180036258  mov     rcx, [rax]
0x18003625b  cmp     [rcx+8], rax
0x18003625f  jnz     loc_1800362E5
0x180036265  mov     [rbx], rcx
0x180036268  mov     [rcx+8], rbx
0x18003626c  mov     [rsp+28h+arg_8], rax
0x180036271  cmp     rax, rbx
0x180036274  jz      short loc_18003628A
0x180036276  lea     rcx, [rsp+28h+arg_8]
0x18003627b  call    FreeMSMSecMemory
0x180036280  mov     rax, [rsp+28h+arg_8]
0x180036285  cmp     rax, rbx
0x180036288  jnz     short loc_180036247
0x18003628a  mov     rcx, rdi; lpCriticalSection
0x18003628d  xor     ebx, ebx
0x18003628f  call    cs:__imp_DeleteCriticalSection
0x180036296  nop     dword ptr [rax+rax+00h]
0x18003629b  lea     rcx, [rsp+28h+arg_0]
0x1800362a0  call    FreeMSMSecMemory
0x1800362a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800362ac  cmp     rcx, rsi
0x1800362af  jz      short loc_1800362D2
0x1800362b1  test    dword ptr [rcx+44h], 100h
0x1800362b8  jz      short loc_1800362D2
0x1800362ba  mov     rcx, [rcx+38h]
0x1800362be  lea     r8, WPP_622467b8f14e3d8e631d784b31d192ed_Traceguids
0x1800362c5  mov     edx, 1Ah
0x1800362ca  mov     r9d, ebx
0x1800362cd  call    WPP_SF_d
0x1800362d2  mov     rsi, [rsp+28h+arg_18]
0x1800362d7  mov     eax, ebx
0x1800362d9  mov     rbx, [rsp+28h+arg_10]
0x1800362de  add     rsp, 20h
0x1800362e2  pop     rdi
0x1800362e3  retn
0x1800362e5  mov     ecx, 3
0x1800362ea  int     29h; Win8: RtlFailFast(ecx)
```
