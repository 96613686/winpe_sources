# VPNIKEConnection::UpdatePeerAdditionalAddresses(_ADDITIONAL_ADDRESSES_ &)

- ea: `0x180013450`
- end: `0x1800135a7`
- name: `?UpdatePeerAdditionalAddresses@VPNIKEConnection@@UEAAXAEAU_ADDITIONAL_ADDRESSES_@@@Z`
- size: `343`
- prototype: `void __fastcall(VPNIKEConnection *__hidden this, struct _ADDITIONAL_ADDRESSES_ *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18001bd20`
- `0x18001f240`

## callees

- `0x180007794`
- `0x180013450`
- `0x1800768d4`
- `0x180076990`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001350c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013537`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001350c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013537`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800134fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013529`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800134fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013529`

## string_xrefs

- `0x1800134e1`: `VPNIKEConnection::UpdatePeerAdditionalAddresses`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall VPNIKEConnection::UpdatePeerAdditionalAddresses(
        VPNIKEConnection *this,
        struct _ADDITIONAL_ADDRESSES_ *a2)
{
  void *v4; // rdi
  HANDLE ProcessHeap; // rax
  void *v6; // rdi
  HANDLE v7; // rax
  __int64 v8; // [rsp+30h] [rbp-68h] BYREF
  __int128 v9; // [rsp+38h] [rbp-60h]
  __int128 v10; // [rsp+48h] [rbp-50h]
  __int64 v11; // [rsp+58h] [rbp-40h]
  int v12; // [rsp+60h] [rbp-38h]
  int v13; // [rsp+64h] [rbp-34h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids);
  }
  v9 = 0;
  v8 = 0;
  v10 = 0;
  v11 = 0;
  v12 = -1;
  v13 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v8,
      L"VPNIKEConnection::UpdatePeerAdditionalAddresses",
      0,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithVpnParams,
      *((void **)this + 14));
  v4 = (void *)*((_QWORD *)this + 38);
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    *((_QWORD *)this + 38) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 39);
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
  }
  *(_OWORD *)((char *)this + 296) = 0;
  *((_QWORD *)this + 39) = 0;
  *(_OWORD *)((char *)this + 296) = *(_OWORD *)a2;
  *((_QWORD *)this + 39) = *((_QWORD *)a2 + 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids);
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v8);
}

```

## disassembly

```asm
0x180013450  push    rbx
0x180013452  push    rsi
0x180013453  push    rdi
0x180013454  push    r14
0x180013456  sub     rsp, 78h
0x18001345a  mov     rsi, rdx
0x18001345d  mov     rbx, rcx
0x180013460  lea     r14, WPP_GLOBAL_Control
0x180013467  mov     rcx, cs:WPP_GLOBAL_Control
0x18001346e  cmp     rcx, r14
0x180013471  jz      short loc_180013494
0x180013473  test    byte ptr [rcx+1Ch], 1
0x180013477  jz      short loc_180013494
0x180013479  cmp     byte ptr [rcx+19h], 6
0x18001347d  jb      short loc_180013494
0x18001347f  mov     edx, 6Ch ; 'l'
0x180013484  lea     r8, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x18001348b  mov     rcx, [rcx+10h]
0x18001348f  call    WPP_SF_
0x180013494  xorps   xmm0, xmm0
0x180013497  movdqu  [rsp+98h+var_60], xmm0
0x18001349d  mov     [rsp+98h+var_68], 0
0x1800134a6  movdqu  [rsp+98h+var_50], xmm0
0x1800134ac  mov     [rsp+98h+var_40], 0
0x1800134b5  mov     [rsp+98h+var_38], 0FFFFFFFFh
0x1800134bd  mov     [rsp+98h+var_34], 0
0x1800134c5  test    cs:byte_1800AA941, 8
0x1800134cc  jz      short loc_1800134F2
0x1800134ce  mov     rax, [rbx+70h]
0x1800134d2  mov     [rsp+98h+var_78], rax; void *
0x1800134d7  lea     r9, ?RasVpnIkeTraceFunctionWithVpnParams@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x1800134de  xor     r8d, r8d; unsigned int *
0x1800134e1  lea     rdx, aVpnikeconnecti_14; "VPNIKEConnection::UpdatePeerAdditionalA"...
0x1800134e8  lea     rcx, [rsp+98h+var_68]; this
0x1800134ed  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x1800134f2  mov     rdi, [rbx+130h]
0x1800134f9  test    rdi, rdi
0x1800134fc  jz      short loc_18001351D
0x1800134fe  call    cs:__imp_GetProcessHeap
0x180013504  mov     r8, rdi; lpMem
0x180013507  xor     edx, edx; dwFlags
0x180013509  mov     rcx, rax; hHeap
0x18001350c  call    cs:__imp_HeapFree
0x180013512  mov     qword ptr [rbx+130h], 0
0x18001351d  mov     rdi, [rbx+138h]
0x180013524  test    rdi, rdi
0x180013527  jz      short loc_18001353D
0x180013529  call    cs:__imp_GetProcessHeap
0x18001352f  mov     r8, rdi; lpMem
0x180013532  xor     edx, edx; dwFlags
0x180013534  mov     rcx, rax; hHeap
0x180013537  call    cs:__imp_HeapFree
0x18001353d  xorps   xmm0, xmm0
0x180013540  xor     eax, eax
0x180013542  movups  xmmword ptr [rbx+128h], xmm0
0x180013549  mov     [rbx+138h], rax
0x180013550  movups  xmm0, xmmword ptr [rsi]
0x180013553  movups  xmmword ptr [rbx+128h], xmm0
0x18001355a  movsd   xmm1, qword ptr [rsi+10h]
0x18001355f  movsd   qword ptr [rbx+138h], xmm1
0x180013567  mov     rcx, cs:WPP_GLOBAL_Control
0x18001356e  cmp     rcx, r14
0x180013571  jz      short loc_180013593
0x180013573  test    byte ptr [rcx+1Ch], 1
0x180013577  jz      short loc_180013593
0x180013579  cmp     byte ptr [rcx+19h], 6
0x18001357d  jb      short loc_180013593
0x18001357f  lea     edx, [rax+6Dh]
0x180013582  lea     r8, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x180013589  mov     rcx, [rcx+10h]
0x18001358d  call    WPP_SF_
0x180013592  nop
0x180013593  lea     rcx, [rsp+98h+var_68]; this
0x180013598  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18001359d  add     rsp, 78h
0x1800135a1  pop     r14
0x1800135a3  pop     rdi
0x1800135a4  pop     rsi
0x1800135a5  pop     rbx
0x1800135a6  retn
```
