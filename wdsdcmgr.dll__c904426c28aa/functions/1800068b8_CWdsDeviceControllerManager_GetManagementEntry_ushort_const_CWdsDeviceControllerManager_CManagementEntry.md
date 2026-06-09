# CWdsDeviceControllerManager::GetManagementEntry(ushort const *,CWdsDeviceControllerManager::CManagementEntry * *)

- ea: `0x1800068b8`
- end: `0x1800069d6`
- name: `?GetManagementEntry@CWdsDeviceControllerManager@@AEAAKPEBGPEAPEAUCManagementEntry@1@@Z`
- size: `286`
- prototype: `unsigned int(CWdsDeviceControllerManager *__hidden this, const unsigned __int16 *, struct CWdsDeviceControllerManager::CManagementEntry **)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180002bd8`
- `0x180005430`
- `0x18000563c`
- `0x180005818`
- `0x18000600c`
- `0x1800063b4`

## callees

- `0x1800068b8`
- `0x180014d58`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000697b`
- `msvcrt!_wcsicmp` at `0x18000697b`

## pseudocode

```c
__int64 __fastcall CWdsDeviceControllerManager::GetManagementEntry(
        CWdsDeviceControllerManager *this,
        const unsigned __int16 *a2,
        struct CWdsDeviceControllerManager::CManagementEntry **a3)
{
  const wchar_t *v3; // r14
  struct CWdsDeviceControllerManager::CManagementEntry *v6; // rsi
  int v7; // ecx
  int v8; // r15d
  unsigned int v9; // r9d
  unsigned int v10; // edi
  unsigned int v11; // ecx
  unsigned int v12; // ebp
  __int64 v13; // r13

  v3 = a2;
  v6 = 0;
  if ( !a2 )
  {
    v3 = (const wchar_t *)*((_QWORD *)this + 40);
    if ( !v3 && *((_DWORD *)this + 49) == 1 )
    {
      v7 = *((_DWORD *)this + 49);
      if ( v7 )
        v6 = (struct CWdsDeviceControllerManager::CManagementEntry *)**((_QWORD **)this + 23);
      v8 = 1413;
      v9 = 2969;
      if ( v7 )
        v8 = 0;
      v10 = v8;
      v11 = v8;
LABEL_17:
      if ( !(unsigned int)ElValidateWin32(
                            v11,
                            0,
                            "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                            v9) )
LABEL_18:
        *a3 = v6;
      return v10;
    }
  }
  v12 = 0;
  if ( !*((_DWORD *)this + 49) )
  {
LABEL_16:
    v10 = 2;
    v9 = 3003;
    v11 = 2;
    goto LABEL_17;
  }
  while ( 1 )
  {
    v13 = 0;
    v10 = 0;
    if ( v12 < *((_DWORD *)this + 49) )
      v13 = *(_QWORD *)(*((_QWORD *)this + 23) + 8LL * v12);
    else
      v10 = 1413;
    if ( (unsigned int)ElValidateWin32(
                         v10,
                         0,
                         "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                         0xBAEu) )
      return v10;
    if ( !_wcsicmp(v3, *(const wchar_t **)(*(_QWORD *)(v13 + 8) + 8LL)) )
    {
      v6 = (struct CWdsDeviceControllerManager::CManagementEntry *)v13;
      goto LABEL_18;
    }
    if ( ++v12 >= *((_DWORD *)this + 49) )
      goto LABEL_16;
  }
}

```

## disassembly

```asm
0x1800068b8  mov     [rsp+arg_0], rbx
0x1800068bd  mov     [rsp+arg_8], rbp
0x1800068c2  mov     [rsp+arg_10], rsi
0x1800068c7  push    rdi
0x1800068c8  push    r12
0x1800068ca  push    r13
0x1800068cc  push    r14
0x1800068ce  push    r15
0x1800068d0  sub     rsp, 20h
0x1800068d4  mov     r14, rdx
0x1800068d7  mov     r12, r8
0x1800068da  xor     edx, edx; char *
0x1800068dc  mov     rbx, rcx
0x1800068df  mov     esi, edx
0x1800068e1  test    r14, r14
0x1800068e4  jnz     short loc_180006929
0x1800068e6  mov     r14, [rcx+140h]
0x1800068ed  test    r14, r14
0x1800068f0  jnz     short loc_180006929
0x1800068f2  cmp     dword ptr [rcx+0C4h], 1
0x1800068f9  jnz     short loc_180006929
0x1800068fb  mov     ecx, [rcx+0C4h]
0x180006901  test    ecx, ecx
0x180006903  jz      short loc_18000690F
0x180006905  mov     rax, [rbx+0B8h]
0x18000690c  mov     rsi, [rax]
0x18000690f  test    ecx, ecx
0x180006911  mov     r15d, 585h
0x180006917  mov     r9d, 0B99h
0x18000691d  cmovnz  r15d, edx
0x180006921  mov     edi, r15d
0x180006924  mov     ecx, r15d
0x180006927  jmp     short loc_18000699E
0x180006929  mov     ebp, edx
0x18000692b  cmp     [rcx+0C4h], edx
0x180006931  jbe     short loc_180006991
0x180006933  mov     r15d, 585h
0x180006939  mov     r13, rdx
0x18000693c  mov     edi, edx
0x18000693e  cmp     ebp, [rbx+0C4h]
0x180006944  jb      short loc_18000694B
0x180006946  mov     edi, r15d
0x180006949  jmp     short loc_180006958
0x18000694b  mov     rax, [rbx+0B8h]
0x180006952  mov     ecx, ebp
0x180006954  mov     r13, [rax+rcx*8]
0x180006958  mov     r9d, 0BAEh; unsigned int
0x18000695e  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180006965  mov     ecx, edi; unsigned int
0x180006967  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000696c  test    eax, eax
0x18000696e  jnz     short loc_1800069B2
0x180006970  mov     rdx, [r13+8]
0x180006974  mov     rcx, r14; String1
0x180006977  mov     rdx, [rdx+8]; String2
0x18000697b  call    cs:__imp__wcsicmp
0x180006981  xor     edx, edx; char *
0x180006983  test    eax, eax
0x180006985  jz      short loc_1800069D1
0x180006987  inc     ebp
0x180006989  cmp     ebp, [rbx+0C4h]
0x18000698f  jb      short loc_180006939
0x180006991  mov     edi, 2
0x180006996  mov     r9d, 0BBBh; unsigned int
0x18000699c  mov     ecx, edi; unsigned int
0x18000699e  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800069a5  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800069aa  test    eax, eax
0x1800069ac  jnz     short loc_1800069B2
0x1800069ae  mov     [r12], rsi
0x1800069b2  mov     rbx, [rsp+48h+arg_0]
0x1800069b7  mov     eax, edi
0x1800069b9  mov     rbp, [rsp+48h+arg_8]
0x1800069be  mov     rsi, [rsp+48h+arg_10]
0x1800069c3  add     rsp, 20h
0x1800069c7  pop     r15
0x1800069c9  pop     r14
0x1800069cb  pop     r13
0x1800069cd  pop     r12
0x1800069cf  pop     rdi
0x1800069d0  retn
0x1800069d1  mov     rsi, r13
0x1800069d4  jmp     short loc_1800069AE
```
