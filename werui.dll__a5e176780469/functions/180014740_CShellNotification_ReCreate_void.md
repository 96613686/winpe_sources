# CShellNotification::ReCreate(void)

- ea: `0x180014740`
- end: `0x1800147df`
- name: `?ReCreate@CShellNotification@@QEAAJXZ`
- size: `159`
- prototype: `__int64 __fastcall(CShellNotification *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180014674`

## callees

- `0x1800035dc`
- `0x180003fe4`
- `0x180013ef0`
- `0x180014438`
- `0x18001447c`
- `0x180014740`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180014756`
- `KERNEL32!EnterCriticalSection` at `0x180014756`
- `KERNEL32!GetLastError` at `0x1800147b9`
- `KERNEL32!GetLastError` at `0x1800147b9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CShellNotification::ReCreate(CShellNotification *this)
{
  unsigned int v2; // ebx
  DWORD LastError; // eax
  char *v5; // [rsp+20h] [rbp-18h] BYREF
  char v6; // [rsp+28h] [rbp-10h]

  v5 = (char *)this + 24;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v6 = 1;
  if ( (unsigned int)CShellNotification::IsCreated(this) )
  {
    v2 = -2147467259;
    if ( !(unsigned int)CShellNotification::InvokeShell_NotifyIcon(
                          this,
                          0,
                          (struct _NOTIFYICONDATAW *)((char *)this + 88)) )
    {
      LastError = GetLastError();
      v2 = ERROR_HR_FROM_WIN32(LastError);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_721966d903033a5712e56ad66803da37_Traceguids);
    v2 = -2147019873;
  }
  utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(&v5);
  return v2;
}

```

## disassembly

```asm
0x180014740  mov     [rsp+arg_0], rbx
0x180014745  push    rdi
0x180014746  sub     rsp, 30h
0x18001474a  mov     rdi, rcx
0x18001474d  add     rcx, 18h; lpCriticalSection
0x180014751  mov     [rsp+38h+var_18], rcx
0x180014756  call    cs:__imp_EnterCriticalSection
0x18001475c  mov     [rsp+38h+var_10], 1
0x180014761  mov     rcx, rdi; this
0x180014764  call    ?IsCreated@CShellNotification@@QEAAHXZ; CShellNotification::IsCreated(void)
0x180014769  test    eax, eax
0x18001476b  jnz     short loc_1800147A2
0x18001476d  lea     rax, WPP_GLOBAL_Control
0x180014774  mov     rcx, cs:WPP_GLOBAL_Control
0x18001477b  cmp     rcx, rax
0x18001477e  jz      short loc_18001479B
0x180014780  test    byte ptr [rcx+1Ch], 1
0x180014784  jz      short loc_18001479B
0x180014786  mov     edx, 15h
0x18001478b  lea     r8, WPP_721966d903033a5712e56ad66803da37_Traceguids
0x180014792  mov     rcx, [rcx+10h]
0x180014796  call    WPP_SF_
0x18001479b  mov     ebx, 8007139Fh
0x1800147a0  jmp     short loc_1800147C8
0x1800147a2  mov     ebx, 80004005h
0x1800147a7  lea     r8, [rdi+58h]; struct _NOTIFYICONDATAW *
0x1800147ab  xor     edx, edx; unsigned int
0x1800147ad  mov     rcx, rdi; this
0x1800147b0  call    ?InvokeShell_NotifyIcon@CShellNotification@@AEAAHKPEAU_NOTIFYICONDATAW@@@Z; CShellNotification::InvokeShell_NotifyIcon(ulong,_NOTIFYICONDATAW *)
0x1800147b5  test    eax, eax
0x1800147b7  jnz     short loc_1800147C8
0x1800147b9  call    cs:__imp_GetLastError
0x1800147bf  mov     ecx, eax; unsigned int
0x1800147c1  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800147c6  mov     ebx, eax
0x1800147c8  lea     rcx, [rsp+38h+var_18]
0x1800147cd  call    ??1?$unique_lock@Vrecursive_mutex@utl@@@utl@@QEAA@XZ; utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(void)
0x1800147d2  mov     eax, ebx
0x1800147d4  mov     rbx, [rsp+38h+arg_0]
0x1800147d9  add     rsp, 30h
0x1800147dd  pop     rdi
0x1800147de  retn
```
