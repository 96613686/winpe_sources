# CContentDropTarget::_GenerateUniqueName(ushort const *,ushort *,ulong,IPortableDevice *,IPortableDeviceContent *,ushort const *,COPY_THREAD_DATA *)

- ea: `0x1800405e8`
- end: `0x18004082c`
- name: `?_GenerateUniqueName@CContentDropTarget@@AEAAJPEBGPEAGKPEAUIPortableDevice@@PEAUIPortableDeviceContent@@0PEAVCOPY_THREAD_DATA@@@Z`
- size: `580`
- prototype: `__int64 __usercall@<rax>(CContentDropTarget *__hidden this@<rcx>, wchar_t *FullPath@<rdx>, unsigned __int16 *@<r8>, unsigned int@<r9d>, struct IPortableDevice *, struct IPortableDeviceContent *, const unsigned __int16 *, struct COPY_THREAD_DATA *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180019e44`
- `0x18003ee9c`

## callees

- `0x180004110`
- `0x180015a90`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x1800405e8`
- `0x18006d310`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800406cc`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800406cc`
- `KERNEL32!LocalFree` at `0x18004072e`
- `KERNEL32!LocalFree` at `0x18004072e`
- `USER32!LoadStringW` at `0x1800406e6`
- `USER32!LoadStringW` at `0x180040797`
- `USER32!LoadStringW` at `0x1800406e6`
- `USER32!LoadStringW` at `0x180040797`

## pseudocode

```c
__int64 __fastcall CContentDropTarget::_GenerateUniqueName(
        CContentDropTarget *this,
        wchar_t *FullPath,
        unsigned __int16 *a3,
        __int64 a4,
        struct IPortableDevice *a5,
        struct IPortableDeviceContent *a6,
        unsigned __int16 *a7,
        struct COPY_THREAD_DATA *a8)
{
  const unsigned __int16 *v11; // r10
  unsigned int v12; // ebx
  int v13; // edi
  HLOCAL v14; // r10
  int CanCreateObject; // eax
  int v17; // [rsp+50h] [rbp-B0h] BYREF
  struct COPY_THREAD_DATA *v18; // [rsp+58h] [rbp-A8h]
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Ext[264]; // [rsp+270h] [rbp+170h] BYREF
  wchar_t Filename[264]; // [rsp+480h] [rbp+380h] BYREF
  unsigned __int16 v22[264]; // [rsp+690h] [rbp+590h] BYREF

  v18 = a8;
  v17 = 0;
  memset_0(v22, 0, 0x208u);
  memset_0(Buffer, 0, 0x208u);
  memset_0(Filename, 0, 0x208u);
  memset_0(Ext, 0, 0x208u);
  _wsplitpath_s(FullPath, 0, 0, 0, 0, Filename, 0x104u, Ext, 0x104u);
  LoadStringW(g_hInst, 0x2407u, Buffer, 260);
  v11 = FormatString(Buffer, Filename, Ext);
  if ( !v11 )
  {
LABEL_2:
    v12 = -2147024882;
LABEL_10:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, v12);
    return v12;
  }
  v13 = 1;
  while ( 1 )
  {
    StringCchCopyW(a3, 0x104u, v11);
    LocalFree(v14);
    CanCreateObject = CContentDropTarget::_CanCreateObject(this, a3, a7, a5, a6, (CProgressUI **)v18, v22, 0x104u, &v17);
    v12 = CanCreateObject;
    if ( CanCreateObject != -2147024713 )
      break;
    if ( v13 == 1 )
      LoadStringW(g_hInst, 0x2408u, Buffer, 260);
    v11 = FormatString(Buffer, Filename, (unsigned int)++v13, Ext);
    if ( !v11 )
      goto LABEL_2;
  }
  if ( CanCreateObject < 0 )
    goto LABEL_10;
  return v12;
}

```

## disassembly

```asm
0x1800405e8  mov     [rsp-8+arg_18], rbx
0x1800405ed  push    rbp
0x1800405ee  push    rsi
0x1800405ef  push    rdi
0x1800405f0  push    r12
0x1800405f2  push    r13
0x1800405f4  push    r14
0x1800405f6  push    r15
0x1800405f8  lea     rbp, [rsp-7B0h]
0x180040600  sub     rsp, 8B0h
0x180040607  mov     rax, cs:__security_cookie
0x18004060e  xor     rax, rsp
0x180040611  mov     [rbp+7E0h+var_40], rax
0x180040618  mov     rax, [rbp+7E0h+arg_38]
0x18004061f  mov     rsi, r8
0x180040622  mov     r15, [rbp+7E0h+arg_20]
0x180040629  mov     rbx, rdx
0x18004062c  mov     r12, [rbp+7E0h+arg_28]
0x180040633  mov     r14, rcx
0x180040636  mov     r13, [rbp+7E0h+arg_30]
0x18004063d  lea     rcx, [rbp+7E0h+var_250]; void *
0x180040644  mov     edi, 208h
0x180040649  mov     [rsp+8E0h+var_888], rax
0x18004064e  mov     r8d, edi; Size
0x180040651  mov     [rsp+8E0h+var_890], 0
0x180040659  xor     edx, edx; Val
0x18004065b  call    memset_0
0x180040660  mov     r8d, edi; Size
0x180040663  lea     rcx, [rsp+8E0h+Buffer]; void *
0x180040668  xor     edx, edx; Val
0x18004066a  call    memset_0
0x18004066f  mov     r8d, edi; Size
0x180040672  lea     rcx, [rbp+7E0h+var_460]; void *
0x180040679  xor     edx, edx; Val
0x18004067b  call    memset_0
0x180040680  mov     r8d, edi; Size
0x180040683  lea     rcx, [rbp+7E0h+var_670]; void *
0x18004068a  xor     edx, edx; Val
0x18004068c  call    memset_0
0x180040691  mov     edi, 104h
0x180040696  lea     rax, [rbp+7E0h+var_670]
0x18004069d  mov     [rsp+8E0h+ExtCount], rdi; ExtCount
0x1800406a2  xor     r9d, r9d; Dir
0x1800406a5  mov     [rsp+8E0h+Ext], rax; Ext
0x1800406aa  xor     r8d, r8d; DriveCount
0x1800406ad  lea     rax, [rbp+7E0h+var_460]
0x1800406b4  mov     [rsp+8E0h+FilenameCount], rdi; FilenameCount
0x1800406b9  mov     [rsp+8E0h+Filename], rax; Filename
0x1800406be  xor     edx, edx; Drive
0x1800406c0  mov     rcx, rbx; FullPath
0x1800406c3  mov     [rsp+8E0h+DirCount], 0; DirCount
0x1800406cc  call    cs:__imp__wsplitpath_s
0x1800406d2  mov     rcx, cs:g_hInst; hInstance
0x1800406d9  lea     r8, [rsp+8E0h+Buffer]; lpBuffer
0x1800406de  mov     r9d, edi; cchBufferMax
0x1800406e1  mov     edx, 2407h; uID
0x1800406e6  call    cs:__imp_LoadStringW
0x1800406ec  lea     r8, [rbp+7E0h+var_670]
0x1800406f3  lea     rdx, [rbp+7E0h+var_460]
0x1800406fa  lea     rcx, [rsp+8E0h+Buffer]; lpSource
0x1800406ff  call    ?FormatString@@YAPEAGPEBGZZ; FormatString(ushort const *,...)
0x180040704  mov     r10, rax
0x180040707  test    rax, rax
0x18004070a  jnz     short loc_180040716
0x18004070c  mov     ebx, 8007000Eh
0x180040711  jmp     loc_1800407CF
0x180040716  mov     edi, 1
0x18004071b  mov     r8, r10; unsigned __int16 *
0x18004071e  mov     edx, 104h; unsigned __int64
0x180040723  mov     rcx, rsi; unsigned __int16 *
0x180040726  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004072b  mov     rcx, r10; hMem
0x18004072e  call    cs:__imp_LocalFree
0x180040734  lea     rax, [rsp+8E0h+var_890]
0x180040739  mov     r9, r15; struct IPortableDevice *
0x18004073c  mov     [rsp+8E0h+ExtCount], rax; int *
0x180040741  mov     r8, r13; unsigned __int16 *
0x180040744  mov     dword ptr [rsp+8E0h+Ext], 104h; unsigned int
0x18004074c  lea     rax, [rbp+7E0h+var_250]
0x180040753  mov     [rsp+8E0h+FilenameCount], rax; unsigned __int16 *
0x180040758  mov     rdx, rsi; unsigned __int16 *
0x18004075b  mov     rax, [rsp+8E0h+var_888]
0x180040760  mov     rcx, r14; this
0x180040763  mov     [rsp+8E0h+Filename], rax; struct COPY_THREAD_DATA *
0x180040768  mov     [rsp+8E0h+DirCount], r12; struct IPortableDeviceContent *
0x18004076d  call    ?_CanCreateObject@CContentDropTarget@@AEAAJPEBG0PEAUIPortableDevice@@PEAUIPortableDeviceContent@@PEAVCOPY_THREAD_DATA@@PEAGIPEAH@Z; CContentDropTarget::_CanCreateObject(ushort const *,ushort const *,IPortableDevice *,IPortableDeviceContent *,COPY_THREAD_DATA *,ushort *,uint,int *)
0x180040772  mov     ebx, eax
0x180040774  cmp     eax, 800700B7h
0x180040779  jnz     short loc_1800407CB
0x18004077b  cmp     edi, 1
0x18004077e  jnz     short loc_18004079D
0x180040780  mov     rcx, cs:g_hInst; hInstance
0x180040787  lea     r8, [rsp+8E0h+Buffer]; lpBuffer
0x18004078c  mov     r9d, 104h; cchBufferMax
0x180040792  mov     edx, 2408h; uID
0x180040797  call    cs:__imp_LoadStringW
0x18004079d  inc     edi
0x18004079f  lea     r9, [rbp+7E0h+var_670]
0x1800407a6  mov     r8d, edi
0x1800407a9  lea     rdx, [rbp+7E0h+var_460]
0x1800407b0  lea     rcx, [rsp+8E0h+Buffer]; lpSource
0x1800407b5  call    ?FormatString@@YAPEAGPEBGZZ; FormatString(ushort const *,...)
0x1800407ba  mov     r10, rax
0x1800407bd  test    rax, rax
0x1800407c0  jnz     loc_18004071B
0x1800407c6  jmp     loc_18004070C
0x1800407cb  test    eax, eax
0x1800407cd  jns     short loc_180040800
0x1800407cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800407d6  lea     rax, WPP_GLOBAL_Control
0x1800407dd  cmp     rcx, rax
0x1800407e0  jz      short loc_180040800
0x1800407e2  test    byte ptr [rcx+1Ch], 2
0x1800407e6  jz      short loc_180040800
0x1800407e8  mov     rcx, [rcx+10h]
0x1800407ec  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x1800407f3  mov     edx, 7Ah ; 'z'
0x1800407f8  mov     r9d, ebx
0x1800407fb  call    WPP_SF_d
0x180040800  mov     eax, ebx
0x180040802  mov     rcx, [rbp+7E0h+var_40]
0x180040809  xor     rcx, rsp; StackCookie
0x18004080c  call    __security_check_cookie
0x180040811  mov     rbx, [rsp+8E0h+arg_18]
0x180040819  add     rsp, 8B0h
0x180040820  pop     r15
0x180040822  pop     r14
0x180040824  pop     r13
0x180040826  pop     r12
0x180040828  pop     rdi
0x180040829  pop     rsi
0x18004082a  pop     rbp
0x18004082b  retn
```
