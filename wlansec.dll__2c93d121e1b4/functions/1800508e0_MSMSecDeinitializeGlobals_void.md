# MSMSecDeinitializeGlobals(void)

- ea: `0x1800508e0`
- end: `0x180050a58`
- name: `?MSMSecDeinitializeGlobals@@YAXXZ`
- size: `376`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180050648`

## callees

- `0x18000892c`
- `0x180008998`
- `0x1800508e0`
- `0x180050a60`
- `0x180050e8c`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x1800509ae`
- `MobileNetworking!ReleaseWriteLock` at `0x1800509ae`
- `MobileNetworking!AcquireWriteLock` at `0x180050962`
- `MobileNetworking!AcquireWriteLock` at `0x180050962`

## pseudocode

```c
void MSMSecDeinitializeGlobals(void)
{
  PVOID *v0; // rcx
  BOOL v1; // ebx
  bool v2; // di
  const char *v3; // r9
  const char *v4; // rax

  v0 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 42, &WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids);
      v0 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v0 != &WPP_GLOBAL_Control && (*((_BYTE *)v0 + 68) & 2) != 0 )
      WPP_SF_(v0[7], 43, &WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids);
  }
  AcquireWriteLock(&g_MSMSecState, qword_1800AEFC0, "MSMSecDeinitializeGlobals", 359);
  v1 = qword_1800AF028 == (_QWORD)&qword_1800AF028;
  v2 = qword_1800AF038 == (_QWORD)&qword_1800AF038;
  ReleaseWriteLock(&g_MSMSecState, qword_1800AEFC0, "MSMSecDeinitializeGlobals", 362);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
  {
    v3 = "Empty";
    v4 = "Empty";
    if ( !v2 )
      v4 = "Non-empty";
    if ( !v1 )
      v3 = "Non-empty";
    WPP_SF_ss(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      44,
      (unsigned int)&WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids,
      (_DWORD)v3,
      (__int64)v4);
  }
  MSMSecDeinitializeHelper(1, 1, 1, 1, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 45, &WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids, 0);
}

```

## disassembly

```asm
0x1800508e0  mov     [rsp+arg_0], rbx
0x1800508e5  mov     [rsp+arg_8], rbp
0x1800508ea  push    rdi
0x1800508eb  sub     rsp, 30h
0x1800508ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800508f6  lea     rbp, WPP_GLOBAL_Control
0x1800508fd  cmp     rcx, rbp
0x180050900  jz      short loc_180050947
0x180050902  test    dword ptr [rcx+44h], 100h
0x180050909  jz      short loc_180050927
0x18005090b  mov     rcx, [rcx+38h]
0x18005090f  lea     r8, WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids
0x180050916  mov     edx, 2Ah ; '*'
0x18005091b  call    WPP_SF_
0x180050920  mov     rcx, cs:WPP_GLOBAL_Control
0x180050927  cmp     rcx, rbp
0x18005092a  jz      short loc_180050947
0x18005092c  test    byte ptr [rcx+44h], 2
0x180050930  jz      short loc_180050947
0x180050932  mov     rcx, [rcx+38h]
0x180050936  lea     r8, WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids
0x18005093d  mov     edx, 2Bh ; '+'
0x180050942  call    WPP_SF_
0x180050947  mov     r9d, 167h
0x18005094d  lea     r8, aMsmsecdeinitia_1; "MSMSecDeinitializeGlobals"
0x180050954  lea     rdx, qword_1800AEFC0
0x18005095b  lea     rcx, ?g_MSMSecState@@3UMSMSEC_GLOBAL_STATE@@A; MSMSEC_GLOBAL_STATE g_MSMSecState
0x180050962  call    cs:__imp_AcquireWriteLock
0x180050969  nop     dword ptr [rax+rax+00h]
0x18005096e  xor     ebx, ebx
0x180050970  lea     rax, qword_1800AF028
0x180050977  cmp     cs:qword_1800AF028, rax
0x18005097e  lea     r8, aMsmsecdeinitia_1; "MSMSecDeinitializeGlobals"
0x180050985  lea     rax, qword_1800AF038
0x18005098c  mov     r9d, 16Ah
0x180050992  setz    bl
0x180050995  lea     rdx, qword_1800AEFC0
0x18005099c  cmp     cs:qword_1800AF038, rax
0x1800509a3  lea     rcx, ?g_MSMSecState@@3UMSMSEC_GLOBAL_STATE@@A; MSMSEC_GLOBAL_STATE g_MSMSecState
0x1800509aa  setz    dil
0x1800509ae  call    cs:__imp_ReleaseWriteLock
0x1800509b5  nop     dword ptr [rax+rax+00h]
0x1800509ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800509c1  cmp     rcx, rbp
0x1800509c4  jz      short loc_180050A04
0x1800509c6  test    byte ptr [rcx+44h], 2
0x1800509ca  jz      short loc_180050A04
0x1800509cc  mov     rcx, [rcx+38h]
0x1800509d0  lea     rdx, aNonEmpty; "Non-empty"
0x1800509d7  test    dil, dil
0x1800509da  lea     r9, aEmpty; "Empty"
0x1800509e1  mov     rax, r9
0x1800509e4  lea     r8, WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids
0x1800509eb  cmovz   rax, rdx
0x1800509ef  test    ebx, ebx
0x1800509f1  mov     qword ptr [rsp+38h+var_18], rax
0x1800509f6  cmovz   r9, rdx
0x1800509fa  mov     edx, 2Ch ; ','
0x1800509ff  call    WPP_SF_ss
0x180050a04  mov     ecx, 1; int
0x180050a09  mov     r9d, ecx; int
0x180050a0c  mov     [rsp+38h+var_18], ecx; int
0x180050a10  mov     r8d, ecx; int
0x180050a13  mov     edx, ecx; int
0x180050a15  call    ?MSMSecDeinitializeHelper@@YAXHHHHH@Z; MSMSecDeinitializeHelper(int,int,int,int,int)
0x180050a1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180050a21  cmp     rcx, rbp
0x180050a24  jz      short loc_180050A47
0x180050a26  test    dword ptr [rcx+44h], 100h
0x180050a2d  jz      short loc_180050A47
0x180050a2f  mov     rcx, [rcx+38h]
0x180050a33  lea     r8, WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids
0x180050a3a  mov     edx, 2Dh ; '-'
0x180050a3f  xor     r9d, r9d
0x180050a42  call    WPP_SF_d
0x180050a47  mov     rbx, [rsp+38h+arg_0]
0x180050a4c  mov     rbp, [rsp+38h+arg_8]
0x180050a51  add     rsp, 30h
0x180050a55  pop     rdi
0x180050a56  retn
```
