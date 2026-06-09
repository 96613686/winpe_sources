# CClientLibrary::InitializeUdpSession(CClientLibrary::Session *)

- ea: `0x1800077f4`
- end: `0x180007963`
- name: `?InitializeUdpSession@CClientLibrary@@AEAAKPEAUSession@1@@Z`
- size: `367`
- prototype: `unsigned int __fastcall(CClientLibrary *__hidden this, struct Session *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180009b30`

## callees

- `0x1800017d8`
- `0x18000318c`
- `0x180006dac`
- `0x1800077f4`
- `0x18000a858`
- `0x18000bd5c`
- `0x18000d6d2`
- `0x18000d700`
- `0x18000e010`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180007839`
- `KERNEL32!CreateEventW` at `0x180007839`
- `KERNEL32!GetLastError` at `0x18000784d`
- `KERNEL32!GetLastError` at `0x18000784d`
- `KERNEL32!CloseHandle` at `0x180007931`
- `KERNEL32!CloseHandle` at `0x180007931`

## pseudocode

```c
__int64 __fastcall CClientLibrary::InitializeUdpSession(CClientLibrary *this, struct Session *a2)
{
  void (__fastcall ***v4)(_QWORD, __int64); // rbx
  HANDLE EventW; // rsi
  DWORD LastError; // eax
  __int64 v7; // rdx
  __int64 v8; // rdi
  void *v9; // rax
  __int64 v10; // rax
  bool v11; // zf
  __int64 v12; // r8
  __int64 v13; // rdx
  _BYTE v15[16]; // [rsp+30h] [rbp-108h] BYREF
  int v16; // [rsp+40h] [rbp-F8h]
  int v17; // [rsp+64h] [rbp-D4h]

  v4 = 0;
  memset_0(v15, 0, 0xD8u);
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    v9 = operator new(0x270u, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v9
      || (v10 = CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>(v9),
          (v4 = (void (__fastcall ***)(_QWORD, __int64))v10) == 0) )
    {
      LODWORD(v8) = 8;
LABEL_15:
      CloseHandle(EventW);
      return (unsigned int)v8;
    }
    v11 = *((_DWORD *)a2 + 8) == 4;
    v12 = 2;
    v17 = 1;
    v16 = 2;
    if ( !v11 )
      v12 = 23;
    v8 = (unsigned int)CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::Initialize(v10, this, v12, v15, a2);
    if ( !(unsigned int)ElValidateWin32(v8, v13, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 722) )
    {
      *((_QWORD *)a2 + 266) = EventW;
      *((_QWORD *)a2 + 267) = v4;
    }
  }
  else
  {
    LastError = GetLastError();
    LODWORD(v8) = ElValidateWin32(LastError, v7, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 701);
  }
  if ( (_DWORD)v8 )
  {
    if ( v4 )
    {
      CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::Shutdown(v4);
      (**v4)(v4, 1);
    }
    if ( EventW )
      goto LABEL_15;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800077f4  mov     [rsp+arg_10], rbx
0x1800077f9  push    rbp
0x1800077fa  push    rsi
0x1800077fb  push    rdi
0x1800077fc  sub     rsp, 120h
0x180007803  mov     rax, cs:__security_cookie
0x18000780a  xor     rax, rsp
0x18000780d  mov     [rsp+138h+var_28], rax
0x180007815  mov     rbp, rdx
0x180007818  mov     rdi, rcx
0x18000781b  xor     edx, edx; Val
0x18000781d  lea     rcx, [rsp+138h+var_108]; void *
0x180007822  mov     r8d, 0D8h; Size
0x180007828  xor     ebx, ebx
0x18000782a  call    memset_0
0x18000782f  xor     r9d, r9d; lpName
0x180007832  xor     r8d, r8d; bInitialState
0x180007835  xor     edx, edx; bManualReset
0x180007837  xor     ecx, ecx; lpEventAttributes
0x180007839  call    cs:__imp_CreateEventW
0x180007840  nop     dword ptr [rax+rax+00h]
0x180007845  mov     rsi, rax
0x180007848  test    rax, rax
0x18000784b  jnz     short loc_180007874
0x18000784d  call    cs:__imp_GetLastError
0x180007854  nop     dword ptr [rax+rax+00h]
0x180007859  mov     r9d, 2BDh
0x18000785f  lea     r8, aBaseEcoWdsWdsc_0; "base\\eco\\wds\\wdscsl\\client\\clientl"...
0x180007866  mov     ecx, eax
0x180007868  call    ElValidateWin32
0x18000786d  mov     edi, eax
0x18000786f  jmp     loc_1800078FE
0x180007874  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000787b  mov     ecx, 270h; unsigned __int64
0x180007880  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007885  test    rax, rax
0x180007888  jz      loc_180007929
0x18000788e  mov     rcx, rax
0x180007891  call    ??0?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@QEAA@XZ; CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>(void)
0x180007896  mov     rbx, rax
0x180007899  test    rax, rax
0x18000789c  jz      loc_180007929
0x1800078a2  cmp     dword ptr [rbp+20h], 4
0x1800078a6  lea     r9, [rsp+138h+var_108]
0x1800078ab  mov     r8d, 2
0x1800078b1  mov     [rsp+138h+var_D4], 1
0x1800078b9  mov     [rsp+138h+var_F8], r8d
0x1800078be  mov     rdx, rdi
0x1800078c1  mov     rcx, rbx
0x1800078c4  mov     [rsp+138h+var_118], rbp
0x1800078c9  lea     eax, [r8+15h]
0x1800078cd  cmovnz  r8d, eax
0x1800078d1  call    ?Initialize@?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@QEAAKPEAVCClientLibrary@@HPEAUSocketSetup@@PEAUtagWDS_ENDPOINT@@@Z; CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::Initialize(CClientLibrary *,int,SocketSetup *,tagWDS_ENDPOINT *)
0x1800078d6  mov     r9d, 2D2h
0x1800078dc  lea     r8, aBaseEcoWdsWdsc_0; "base\\eco\\wds\\wdscsl\\client\\clientl"...
0x1800078e3  mov     ecx, eax
0x1800078e5  mov     edi, eax
0x1800078e7  call    ElValidateWin32
0x1800078ec  test    eax, eax
0x1800078ee  jnz     short loc_1800078FE
0x1800078f0  mov     [rbp+850h], rsi
0x1800078f7  mov     [rbp+858h], rbx
0x1800078fe  test    edi, edi
0x180007900  jz      short loc_18000793D
0x180007902  test    rbx, rbx
0x180007905  jz      short loc_180007922
0x180007907  mov     rcx, rbx
0x18000790a  call    ?Shutdown@?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@QEAAKXZ; CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::Shutdown(void)
0x18000790f  mov     rax, [rbx]
0x180007912  mov     edx, 1
0x180007917  mov     rcx, rbx
0x18000791a  mov     rax, [rax]
0x18000791d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007922  test    rsi, rsi
0x180007925  jz      short loc_18000793D
0x180007927  jmp     short loc_18000792E
0x180007929  mov     edi, 8
0x18000792e  mov     rcx, rsi; hObject
0x180007931  call    cs:__imp_CloseHandle
0x180007938  nop     dword ptr [rax+rax+00h]
0x18000793d  mov     eax, edi
0x18000793f  mov     rcx, [rsp+138h+var_28]
0x180007947  xor     rcx, rsp; StackCookie
0x18000794a  call    __security_check_cookie
0x18000794f  mov     rbx, [rsp+138h+arg_10]
0x180007957  add     rsp, 120h
0x18000795e  pop     rdi
0x18000795f  pop     rsi
0x180007960  pop     rbp
0x180007961  retn
```
