# ProcessRouteDelete

- ea: `0x1800158cc`
- end: `0x180015a84`
- name: `ProcessRouteDelete`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800167d0`

## callees

- `0x18000aa60`
- `0x180014d2c`
- `0x180015178`
- `0x1800155fc`
- `0x1800158cc`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800159f4`
- `KERNEL32!HeapFree` at `0x1800159f4`

## pseudocode

```c
__int64 __fastcall ProcessRouteDelete(RTM_DEST_HANDLE *a1)
{
  signed int v2; // ecx
  int v3; // eax
  DWORD OpaqueInformationPointer; // ebx
  unsigned int **v5; // rdi
  unsigned int *v6; // rcx
  __int64 v7; // rax
  __int64 v8; // r8
  const wchar_t *v9; // rdx
  PVOID OpaqueInfoPointer; // [rsp+20h] [rbp-E0h] BYREF
  int v12; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[2044]; // [rsp+34h] [rbp-CCh] BYREF

  OpaqueInfoPointer = 0;
  v12 = 0;
  memset_0(v13, 0, sizeof(v13));
  if ( (unsigned __int64)g_hNotificationHandle == 0x7754DF32
    || (v2 = *(_DWORD *)(((unsigned __int64)g_hNotificationHandle ^ 0x7754DF32) + 0x1C), v2 < 0)
    || (unsigned __int64)*a1 == 0x7754DF32 )
  {
    OpaqueInformationPointer = 6;
    v8 = 6;
    if ( !qword_18002B8A8 )
      return OpaqueInformationPointer;
    v9 = L"Failed to check if dest marked %d";
    goto LABEL_21;
  }
  v3 = *(_DWORD *)(((unsigned __int64)*a1 ^ 0x7754DF32) + 0x28);
  if ( _bittest(&v3, v2) )
  {
    OpaqueInformationPointer = RtmGetOpaqueInformationPointer(g_hRtmHandle, *a1, &OpaqueInfoPointer);
    if ( !OpaqueInformationPointer )
    {
      v5 = *(unsigned int ***)OpaqueInfoPointer;
      if ( *(_QWORD *)OpaqueInfoPointer )
      {
        *(_QWORD *)OpaqueInfoPointer = 0;
        AcquireWriteLock(v5 + 2);
        while ( 1 )
        {
          v6 = *v5;
          if ( *v5 == (unsigned int *)v5 )
            break;
          if ( *((unsigned int ***)v6 + 1) != v5 || (v7 = *(_QWORD *)v6, *(unsigned int **)(*(_QWORD *)v6 + 8LL) != v6) )
            __fastfail(3u);
          *v5 = (unsigned int *)v7;
          *(_QWORD *)(v7 + 8) = v5;
          DeleteMfeAndRefs(v6);
        }
        ReleaseWriteLock((__int64)(v5 + 2));
        HeapFree(hHeap, 0, v5);
        return 0;
      }
    }
    if ( !qword_18002B8A8 )
      return OpaqueInformationPointer;
    v8 = OpaqueInformationPointer;
    v9 = L"Failed to get opaque ptr %d";
LABEL_21:
    LOWORD(v12) = 0;
    FormatRRASErrorString(&v12, v9, v8);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v12);
    return OpaqueInformationPointer;
  }
  if ( qword_18002B8A8 )
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gMgmTemplateFunc)(
      gMgmEtwContext,
      qword_18002B8A8,
      L"Ignoring change notification for unmarked destination");
  return 0;
}

```

## disassembly

```asm
0x1800158cc  mov     [rsp-8+arg_8], rbx
0x1800158d1  mov     [rsp-8+arg_10], rdi
0x1800158d6  push    rbp
0x1800158d7  lea     rbp, [rsp-740h]
0x1800158df  sub     rsp, 840h
0x1800158e6  mov     rax, cs:__security_cookie
0x1800158ed  xor     rax, rsp
0x1800158f0  mov     [rbp+740h+var_10], rax
0x1800158f7  mov     rbx, rcx
0x1800158fa  mov     [rsp+840h+OpaqueInfoPointer], 0
0x180015903  xor     eax, eax
0x180015905  lea     rcx, [rsp+840h+var_80C]; void *
0x18001590a  xor     edx, edx; Val
0x18001590c  mov     [rsp+840h+var_810], eax
0x180015910  mov     r8d, 7FCh; Size
0x180015916  call    memset_0
0x18001591b  mov     rcx, cs:g_hNotificationHandle
0x180015922  mov     edx, 7754DF32h
0x180015927  xor     rcx, rdx
0x18001592a  jz      loc_180015A15
0x180015930  mov     ecx, [rcx+1Ch]
0x180015933  test    ecx, ecx
0x180015935  js      loc_180015A15
0x18001593b  mov     rax, [rbx]
0x18001593e  xor     rax, rdx
0x180015941  jz      loc_180015A15
0x180015947  mov     eax, [rax+28h]
0x18001594a  bt      eax, ecx
0x18001594d  jb      short loc_18001597C
0x18001594f  mov     rdx, cs:qword_18002B8A8
0x180015956  test    rdx, rdx
0x180015959  jz      short loc_180015975
0x18001595b  mov     rcx, cs:gMgmEtwContext
0x180015962  lea     r8, aIgnoringChange; "Ignoring change notification for unmark"...
0x180015969  mov     rax, cs:gMgmTemplateFunc
0x180015970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015975  xor     ebx, ebx
0x180015977  jmp     loc_180015A5E
0x18001597c  mov     rdx, [rbx]; DestHandle
0x18001597f  lea     r8, [rsp+840h+OpaqueInfoPointer]; OpaqueInfoPointer
0x180015984  mov     rcx, cs:g_hRtmHandle; RtmRegHandle
0x18001598b  call    RtmGetOpaqueInformationPointer
0x180015990  mov     ebx, eax
0x180015992  test    eax, eax
0x180015994  jnz     short loc_1800159FF
0x180015996  mov     rax, [rsp+840h+OpaqueInfoPointer]
0x18001599b  mov     rdi, [rax]
0x18001599e  test    rdi, rdi
0x1800159a1  jz      short loc_1800159FF
0x1800159a3  lea     rcx, [rdi+10h]
0x1800159a7  mov     qword ptr [rax], 0
0x1800159ae  call    AcquireWriteLock
0x1800159b3  mov     rcx, [rdi]; lpMem
0x1800159b6  cmp     rcx, rdi
0x1800159b9  jz      short loc_1800159DF
0x1800159bb  cmp     [rcx+8], rdi
0x1800159bf  jnz     short loc_1800159D8
0x1800159c1  mov     rax, [rcx]
0x1800159c4  cmp     [rax+8], rcx
0x1800159c8  jnz     short loc_1800159D8
0x1800159ca  mov     [rdi], rax
0x1800159cd  mov     [rax+8], rdi
0x1800159d1  call    DeleteMfeAndRefs
0x1800159d6  jmp     short loc_1800159B3
0x1800159d8  mov     ecx, 3
0x1800159dd  int     29h; Win8: RtlFailFast(ecx)
0x1800159df  lea     rcx, [rdi+10h]
0x1800159e3  call    ReleaseWriteLock
0x1800159e8  mov     rcx, cs:hHeap; hHeap
0x1800159ef  mov     r8, rdi; lpMem
0x1800159f2  xor     edx, edx; dwFlags
0x1800159f4  call    cs:__imp_HeapFree
0x1800159fa  jmp     loc_180015975
0x1800159ff  cmp     cs:qword_18002B8A8, 0
0x180015a07  jz      short loc_180015A5E
0x180015a09  mov     r8d, ebx
0x180015a0c  lea     rdx, aFailedToGetOpa; "Failed to get opaque ptr %d"
0x180015a13  jmp     short loc_180015A2E
0x180015a15  cmp     cs:qword_18002B8A8, 0
0x180015a1d  mov     ebx, 6
0x180015a22  mov     r8d, ebx
0x180015a25  jz      short loc_180015A5E
0x180015a27  lea     rdx, aFailedToCheckI_0; "Failed to check if dest marked %d"
0x180015a2e  xor     eax, eax
0x180015a30  lea     rcx, [rsp+840h+var_810]
0x180015a35  mov     word ptr [rsp+840h+var_810], ax
0x180015a3a  call    FormatRRASErrorString
0x180015a3f  mov     rdx, cs:qword_18002B8A8
0x180015a46  lea     r8, [rsp+840h+var_810]
0x180015a4b  mov     rcx, cs:gMgmEtwContext
0x180015a52  mov     rax, cs:gMgmTemplateFunc
0x180015a59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a5e  mov     eax, ebx
0x180015a60  mov     rcx, [rbp+740h+var_10]
0x180015a67  xor     rcx, rsp; StackCookie
0x180015a6a  call    __security_check_cookie
0x180015a6f  lea     r11, [rsp+840h+var_s0]
0x180015a77  mov     rbx, [r11+18h]
0x180015a7b  mov     rdi, [r11+20h]
0x180015a7f  mov     rsp, r11
0x180015a82  pop     rbp
0x180015a83  retn
```
