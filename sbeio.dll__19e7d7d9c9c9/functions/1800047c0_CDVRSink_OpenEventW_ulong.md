# CDVRSink::OpenEventW(ulong)

- ea: `0x1800047c0`
- end: `0x1800048ae`
- name: `?OpenEventW@CDVRSink@@MEAAJK@Z`
- size: `238`
- prototype: `__int64 __fastcall(CDVRSink *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800015f0`
- `0x1800047c0`
- `0x1800050cc`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800047f3`
- `KERNEL32!CloseHandle` at `0x1800047f3`
- `KERNEL32!GetLastError` at `0x180004869`
- `KERNEL32!GetLastError` at `0x180004869`
- `KERNEL32!OpenEventW` at `0x180004845`
- `KERNEL32!OpenEventW` at `0x180004845`

## pseudocode

```c
__int64 __fastcall CDVRSink::OpenEventW(CDVRSink *this, unsigned int a2)
{
  __int64 v2; // rsi
  void *v4; // rcx
  int v5; // ebx
  HANDLE v6; // rax
  signed int LastError; // eax
  int v9; // [rsp+20h] [rbp-88h]
  WCHAR Name[40]; // [rsp+30h] [rbp-78h] BYREF

  v2 = a2;
  v4 = (void *)*((_QWORD *)this + a2 + 1206);
  if ( v4 )
  {
    CloseHandle(v4);
    *((_QWORD *)this + v2 + 1206) = 0;
  }
  v9 = *(_DWORD *)(*((_QWORD *)this + 1160) + 40 * v2 + 72);
  v5 = StringCchPrintfW(Name, 0x28u, L"%s%u", L"Global\\_MS_TSDVRASF_EVENT_", v9);
  if ( v5 >= 0 )
  {
    v6 = OpenEventW(2u, 0, Name);
    *((_QWORD *)this + v2 + 1206) = v6;
    if ( v6 )
    {
      *(_DWORD *)(*((_QWORD *)this + 1160) + 40 * v2 + 100) = *(_DWORD *)(*((_QWORD *)this + 1160) + 40 * v2 + 96);
    }
    else
    {
      LastError = GetLastError();
      *((_DWORD *)this + v2 + 2428) = 1;
      v5 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800047c0  mov     [rsp+arg_10], rbx
0x1800047c5  push    rbp
0x1800047c6  push    rsi
0x1800047c7  push    rdi
0x1800047c8  sub     rsp, 90h
0x1800047cf  mov     rax, cs:__security_cookie
0x1800047d6  xor     rax, rsp
0x1800047d9  mov     [rsp+0A8h+var_28], rax
0x1800047e1  mov     esi, edx
0x1800047e3  mov     rdi, rcx
0x1800047e6  mov     rcx, [rcx+rsi*8+25B0h]; hObject
0x1800047ee  test    rcx, rcx
0x1800047f1  jz      short loc_180004805
0x1800047f3  call    cs:__imp_CloseHandle
0x1800047f9  mov     qword ptr [rdi+rsi*8+25B0h], 0
0x180004805  mov     rax, [rdi+2440h]
0x18000480c  lea     rbp, [rsi+rsi*4]
0x180004810  lea     r9, aGlobalMsTsdvra_0; "Global\\_MS_TSDVRASF_EVENT_"
0x180004817  mov     edx, 28h ; '('; unsigned __int64
0x18000481c  lea     r8, aSU; "%s%u"
0x180004823  mov     ecx, [rax+rbp*8+48h]
0x180004827  mov     [rsp+0A8h+var_88], ecx
0x18000482b  lea     rcx, [rsp+0A8h+Name]; unsigned __int16 *
0x180004830  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004835  mov     ebx, eax
0x180004837  test    eax, eax
0x180004839  js      short loc_180004889
0x18000483b  xor     edx, edx; bInheritHandle
0x18000483d  lea     r8, [rsp+0A8h+Name]; lpName
0x180004842  lea     ecx, [rdx+2]; dwDesiredAccess
0x180004845  call    cs:__imp_OpenEventW
0x18000484b  mov     [rdi+rsi*8+25B0h], rax
0x180004853  test    rax, rax
0x180004856  jz      short loc_180004869
0x180004858  mov     rcx, [rdi+2440h]
0x18000485f  mov     eax, [rcx+rbp*8+60h]
0x180004863  mov     [rcx+rbp*8+64h], eax
0x180004867  jmp     short loc_180004889
0x180004869  call    cs:__imp_GetLastError
0x18000486f  mov     dword ptr [rdi+rsi*4+25F0h], 1
0x18000487a  mov     ebx, eax
0x18000487c  test    eax, eax
0x18000487e  jle     short loc_180004889
0x180004880  movzx   ebx, ax
0x180004883  or      ebx, 80070000h
0x180004889  mov     eax, ebx
0x18000488b  mov     rcx, [rsp+0A8h+var_28]
0x180004893  xor     rcx, rsp; StackCookie
0x180004896  call    __security_check_cookie
0x18000489b  mov     rbx, [rsp+0A8h+arg_10]
0x1800048a3  add     rsp, 90h
0x1800048aa  pop     rdi
0x1800048ab  pop     rsi
0x1800048ac  pop     rbp
0x1800048ad  retn
```
