# CContentProvider::OpenContent(void *,ushort const *,unsigned __int64 *,void * *)

- ea: `0x180009e84`
- end: `0x18000a010`
- name: `?OpenContent@CContentProvider@@QEAAKPEAXPEBGPEA_KPEAPEAX@Z`
- size: `396`
- prototype: `unsigned int __usercall@<eax>(LPCRITICAL_SECTION lpCriticalSection@<rcx>, void *@<rdx>, const unsigned __int16 *@<r8>, unsigned __int64 *@<r9>, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003f10`

## callees

- `0x180009e84`
- `0x18000a018`
- `0x18000a160`
- `0x1800227d4`
- `0x180024dec`
- `0x180025850`
- `0x180026d70`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180009ecf`
- `KERNEL32!LeaveCriticalSection` at `0x180009fcd`
- `KERNEL32!LeaveCriticalSection` at `0x180009ecf`
- `KERNEL32!LeaveCriticalSection` at `0x180009fcd`
- `KERNEL32!EnterCriticalSection` at `0x180009ead`
- `KERNEL32!EnterCriticalSection` at `0x180009ead`

## pseudocode

```c
__int64 __fastcall CContentProvider::OpenContent(
        LPCRITICAL_SECTION lpCriticalSection,
        void *a2,
        const unsigned __int16 *a3,
        unsigned __int64 *a4,
        void **a5)
{
  int v9; // edi
  unsigned int ContentSize; // ebx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rbx
  int v12; // eax
  const char *v13; // rdx
  const char *v14; // rdx
  unsigned int v15; // eax
  const char *v16; // rdx
  void *v18; // [rsp+70h] [rbp+8h] BYREF

  v18 = (void *)-1LL;
  EnterCriticalSection(lpCriticalSection);
  v9 = 1;
  if ( !lpCriticalSection[1].LockCount )
  {
    ContentSize = 21;
LABEL_11:
    CEventLog::Log((CEventLog *)&hEventLog, 0xC1210259, 3);
    if ( v18 != (void *)-1LL )
    {
      v15 = CContentProvider::CloseContent(lpCriticalSection, v18);
      ElValidateWin32(v15, v16, "base\\eco\\wds\\transport\\server\\mc\\contentprovider.cpp", 0x2A8u);
    }
    if ( v9 )
      LeaveCriticalSection(lpCriticalSection);
    return ContentSize;
  }
  DebugInfo = lpCriticalSection[3].DebugInfo;
  v9 = 0;
  LeaveCriticalSection(lpCriticalSection);
  v12 = ((__int64 (__fastcall *)(void *, const unsigned __int16 *, void **))DebugInfo)(a2, a3, &v18);
  ContentSize = v12;
  if ( v12 < 0 && (v12 & 0x1FFF0000) == 0x70000 )
    ContentSize = (unsigned __int16)v12;
  if ( !ElValidateWin32(ContentSize, v13, "base\\eco\\wds\\transport\\server\\mc\\contentprovider.cpp", 0x28Cu) )
  {
    if ( !a4
      || (ContentSize = CContentProvider::GetContentSize(lpCriticalSection, v18, a4),
          !ElValidateWin32(ContentSize, v14, "base\\eco\\wds\\transport\\server\\mc\\contentprovider.cpp", 0x295u)) )
    {
      *a5 = v18;
    }
  }
  if ( ContentSize )
    goto LABEL_11;
  return ContentSize;
}

```

## disassembly

```asm
0x180009e84  mov     rax, rsp
0x180009e87  mov     [rax+10h], rbx
0x180009e8b  mov     [rax+18h], rbp
0x180009e8f  mov     [rax+20h], rsi
0x180009e93  push    rdi
0x180009e94  push    r14
0x180009e96  push    r15
0x180009e98  sub     rsp, 50h
0x180009e9c  or      qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x180009ea1  mov     rbp, r9
0x180009ea4  mov     r15, r8
0x180009ea7  mov     r14, rdx
0x180009eaa  mov     rsi, rcx
0x180009ead  call    cs:__imp_EnterCriticalSection
0x180009eb3  cmp     dword ptr [rsi+30h], 0
0x180009eb7  mov     edi, 1
0x180009ebc  jnz     short loc_180009EC6
0x180009ebe  lea     ebx, [rdi+14h]
0x180009ec1  jmp     loc_180009F5D
0x180009ec6  mov     rbx, [rsi+78h]
0x180009eca  mov     rcx, rsi; lpCriticalSection
0x180009ecd  xor     edi, edi
0x180009ecf  call    cs:__imp_LeaveCriticalSection
0x180009ed5  lea     r8, [rsp+68h+arg_0]
0x180009eda  mov     rdx, r15
0x180009edd  mov     rcx, r14
0x180009ee0  mov     rax, rbx
0x180009ee3  call    cs:__guard_dispatch_icall_fptr
0x180009ee9  mov     ebx, eax
0x180009eeb  test    eax, eax
0x180009eed  jns     short loc_180009EFE
0x180009eef  and     eax, 1FFF0000h
0x180009ef4  cmp     eax, 70000h
0x180009ef9  jnz     short loc_180009EFE
0x180009efb  movzx   ebx, bx
0x180009efe  mov     r9d, 28Ch; unsigned int
0x180009f04  lea     r8, aBaseEcoWdsTran_3; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180009f0b  mov     ecx, ebx; unsigned int
0x180009f0d  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180009f12  test    eax, eax
0x180009f14  jnz     short loc_180009F55
0x180009f16  test    rbp, rbp
0x180009f19  jz      short loc_180009F45
0x180009f1b  mov     rdx, [rsp+68h+arg_0]; void *
0x180009f20  mov     r8, rbp; unsigned __int64 *
0x180009f23  mov     rcx, rsi; lpCriticalSection
0x180009f26  call    ?GetContentSize@CContentProvider@@QEAAKPEAXPEA_K@Z; CContentProvider::GetContentSize(void *,unsigned __int64 *)
0x180009f2b  mov     r9d, 295h; unsigned int
0x180009f31  lea     r8, aBaseEcoWdsTran_3; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180009f38  mov     ecx, eax; unsigned int
0x180009f3a  mov     ebx, eax
0x180009f3c  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180009f41  test    eax, eax
0x180009f43  jnz     short loc_180009F55
0x180009f45  mov     rcx, [rsp+68h+arg_20]
0x180009f4d  mov     rdx, [rsp+68h+arg_0]
0x180009f52  mov     [rcx], rdx
0x180009f55  test    ebx, ebx
0x180009f57  jz      loc_180009FF4
0x180009f5d  mov     rax, [rsi+28h]
0x180009f61  lea     rcx, hEventLog; this
0x180009f68  mov     [rsp+68h+var_28], ebx
0x180009f6c  mov     r9d, 1
0x180009f72  mov     [rsp+68h+var_30], 5
0x180009f7a  mov     edx, 0C1210259h; unsigned int
0x180009f7f  mov     [rsp+68h+var_38], r15
0x180009f84  mov     [rsp+68h+var_40], 1
0x180009f8c  lea     r8d, [r9+2]; int
0x180009f90  mov     qword ptr [rsp+68h+var_48], rax; int
0x180009f95  call    ?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x180009f9a  mov     rdx, [rsp+68h+arg_0]; void *
0x180009f9f  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180009fa3  jz      short loc_180009FC1
0x180009fa5  mov     rcx, rsi; lpCriticalSection
0x180009fa8  call    ?CloseContent@CContentProvider@@QEAAKPEAX@Z; CContentProvider::CloseContent(void *)
0x180009fad  mov     ecx, eax; unsigned int
0x180009faf  lea     r8, aBaseEcoWdsTran_3; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180009fb6  mov     r9d, 2A8h; unsigned int
0x180009fbc  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180009fc1  test    edi, edi
0x180009fc3  jz      short loc_180009FF4
0x180009fc5  add     edi, 0FFFFFFFFh
0x180009fc8  jnz     short loc_180009FD3
0x180009fca  mov     rcx, rsi; lpCriticalSection
0x180009fcd  call    cs:__imp_LeaveCriticalSection
0x180009fd3  test    edi, edi
0x180009fd5  jz      short loc_180009FF4
0x180009fd7  and     [rsp+68h+var_48], 0
0x180009fdc  lea     r8, aMUlockcount0; "m_uLockCount == 0"
0x180009fe3  mov     edx, 16Ah; unsigned int
0x180009fe8  lea     rcx, aInternalOnecor_0; "internal\\onecorebase\\private\\inc\\ec"...
0x180009fef  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180009ff4  lea     r11, [rsp+68h+var_18]
0x180009ff9  mov     eax, ebx
0x180009ffb  mov     rbx, [r11+28h]
0x180009fff  mov     rbp, [r11+30h]
0x18000a003  mov     rsi, [r11+38h]
0x18000a007  mov     rsp, r11
0x18000a00a  pop     r15
0x18000a00c  pop     r14
0x18000a00e  pop     rdi
0x18000a00f  retn
```
