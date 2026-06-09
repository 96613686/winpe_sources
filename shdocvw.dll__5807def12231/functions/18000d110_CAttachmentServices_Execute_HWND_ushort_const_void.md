# CAttachmentServices::Execute(HWND__ *,ushort const *,void * *)

- ea: `0x18000d110`
- end: `0x18000d286`
- name: `?Execute@CAttachmentServices@@UEAAJPEAUHWND__@@PEBGPEAPEAX@Z`
- size: `374`
- prototype: `__int64 __fastcall(LPARAM this, HWND hWndParent, const unsigned __int16 *, void **)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, service_task`

## callees

- `0x1800022f0`
- `0x180002d10`
- `0x180003080`
- `0x1800030e0`
- `0x180003f30`
- `0x180004340`
- `0x180009018`
- `0x18000cf8c`
- `0x18000d110`
- `0x180010060`
- `0x180010dbc`
- `0x180010e3c`
- `0x180010f64`
- `0x1800110cc`
- `0x180011148`

## import_xrefs

- `SHELL32!ShellExecuteExW` at `0x18000d217`
- `SHELL32!ShellExecuteExW` at `0x18000d217`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d243`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d243`
- `USER32!IsWindow` at `0x18000d14f`
- `USER32!IsWindow` at `0x18000d14f`

## pseudocode

```c
__int64 __fastcall CAttachmentServices::Execute(LPARAM this, HWND hWndParent, const unsigned __int16 *a3, void **a4)
{
  BOOL v8; // eax
  LPARAM v9; // rcx
  int v10; // edx
  HKEY v11; // rcx
  int v12; // eax
  ULONG v13; // eax
  int Error; // edi
  __int64 v15; // r8
  __int64 v16; // rdx
  unsigned int v18; // [rsp+20h] [rbp-49h] BYREF
  ATTACHMENT_ACTION v19[3]; // [rsp+24h] [rbp-45h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+30h] [rbp-39h] BYREF

  v18 = 0;
  if ( (unsigned int)CAttachmentServices::PushOp(this, 4, &v18) )
  {
    v8 = IsWindow(hWndParent);
    v9 = this;
    if ( !v8 )
    {
      v15 = 0;
      v16 = 2147942487LL;
      goto LABEL_18;
    }
    CAttachmentServices::_OpStaticFileTypeTrust((CAttachmentServices *)this);
    CAttachmentServices::_OpValidateLocalPath((CAttachmentServices *)this);
    CAttachmentServices::_OpTrustedHandler((CAttachmentServices *)this);
    CAttachmentServices::_OpZoneCheck((CAttachmentServices *)this);
    CAttachmentServices::_OpAntiVirus((CAttachmentServices *)this, hWndParent);
    CAttachmentServices::_OpZoneMarking((CAttachmentServices *)this, v10);
    v19[0] = ATTACHMENT_ACTION_CANCEL;
    CAttachmentServices::_OpUserTrust((CAttachmentServices *)this, hWndParent, 2, v19);
    if ( !(unsigned int)CAttachmentServices::Continuable((CAttachmentServices *)this) )
    {
LABEL_19:
      CAttachmentServices::PopOp(this, v18);
      return CAttachmentServices::DetailedResult((CAttachmentServices *)this, hWndParent);
    }
    pExecInfo.cbSize = 112;
    memset_0(&pExecInfo.fMask, 0, 0x6Cu);
    v11 = *(HKEY *)(this + 104);
    pExecInfo.lpFile = *(LPCWSTR *)(this + 40);
    v12 = 0x800000;
    pExecInfo.lpVerb = a3;
    pExecInfo.hwnd = hWndParent;
    pExecInfo.nShow = 1;
    if ( v11 )
    {
      pExecInfo.hkeyClass = v11;
      v12 = 8388611;
    }
    if ( a4 )
      v13 = v12 | 0x140;
    else
      v13 = v12 | 0x100000;
    pExecInfo.fMask = v13;
    if ( ShellExecuteExW(&pExecInfo) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromLastError();
      if ( Error < 0 )
      {
LABEL_16:
        v15 = 1;
        v16 = (unsigned int)Error;
        v9 = this;
LABEL_18:
        CAttachmentServices::ReportResult(v9, v16, v15);
        goto LABEL_19;
      }
    }
    if ( a4 )
    {
      *a4 = pExecInfo.hProcess;
    }
    else if ( pExecInfo.hProcess )
    {
      CloseHandle(pExecInfo.hProcess);
    }
    goto LABEL_16;
  }
  return CAttachmentServices::DetailedResult((CAttachmentServices *)this, hWndParent);
}

```

## disassembly

```asm
0x18000d110  push    rbp
0x18000d112  push    rbx
0x18000d113  push    rsi
0x18000d114  push    rdi
0x18000d115  push    r14
0x18000d117  lea     rbp, [rsp-37h]
0x18000d11c  sub     rsp, 0A0h
0x18000d123  mov     r14, rdx
0x18000d126  mov     [rbp+57h+var_A0], 0
0x18000d12d  mov     rdi, r8
0x18000d130  mov     edx, 4
0x18000d135  lea     r8, [rbp+57h+var_A0]
0x18000d139  mov     rsi, r9
0x18000d13c  mov     rbx, rcx
0x18000d13f  call    ?PushOp@CAttachmentServices@@AEAAHW4ATTACHMENT_OP@@PEAW42@@Z; CAttachmentServices::PushOp(ATTACHMENT_OP,ATTACHMENT_OP *)
0x18000d144  test    eax, eax
0x18000d146  jz      loc_18000D26E
0x18000d14c  mov     rcx, r14; hWnd
0x18000d14f  call    cs:__imp_IsWindow
0x18000d155  mov     rcx, rbx; this
0x18000d158  test    eax, eax
0x18000d15a  jz      loc_18000D256
0x18000d160  call    ?_OpStaticFileTypeTrust@CAttachmentServices@@AEAAXXZ; CAttachmentServices::_OpStaticFileTypeTrust(void)
0x18000d165  mov     rcx, rbx; this
0x18000d168  call    ?_OpValidateLocalPath@CAttachmentServices@@AEAAXXZ; CAttachmentServices::_OpValidateLocalPath(void)
0x18000d16d  mov     rcx, rbx; this
0x18000d170  call    ?_OpTrustedHandler@CAttachmentServices@@AEAAXXZ; CAttachmentServices::_OpTrustedHandler(void)
0x18000d175  mov     rcx, rbx; this
0x18000d178  call    ?_OpZoneCheck@CAttachmentServices@@AEAAXXZ; CAttachmentServices::_OpZoneCheck(void)
0x18000d17d  mov     rdx, r14; HWND
0x18000d180  mov     rcx, rbx; this
0x18000d183  call    ?_OpAntiVirus@CAttachmentServices@@AEAAXPEAUHWND__@@@Z; CAttachmentServices::_OpAntiVirus(HWND__ *)
0x18000d188  mov     rcx, rbx; this
0x18000d18b  call    ?_OpZoneMarking@CAttachmentServices@@AEAAXXZ; CAttachmentServices::_OpZoneMarking(void)
0x18000d190  lea     r9, [rbp+57h+var_9C]; enum ATTACHMENT_ACTION *
0x18000d194  mov     [rbp+57h+var_9C], 0
0x18000d19b  mov     r8d, 2; enum ATTACHMENT_PROMPT
0x18000d1a1  mov     rdx, r14; HWND
0x18000d1a4  mov     rcx, rbx; this
0x18000d1a7  call    ?_OpUserTrust@CAttachmentServices@@AEAAXPEAUHWND__@@W4ATTACHMENT_PROMPT@@PEAW4ATTACHMENT_ACTION@@@Z; CAttachmentServices::_OpUserTrust(HWND__ *,ATTACHMENT_PROMPT,ATTACHMENT_ACTION *)
0x18000d1ac  mov     rcx, rbx; this
0x18000d1af  call    ?Continuable@CAttachmentServices@@AEAAHXZ; CAttachmentServices::Continuable(void)
0x18000d1b4  test    eax, eax
0x18000d1b6  jz      loc_18000D263
0x18000d1bc  xor     edx, edx; Val
0x18000d1be  mov     [rbp+57h+pExecInfo.cbSize], 70h ; 'p'
0x18000d1c5  lea     rcx, [rbp+57h+pExecInfo.fMask]; void *
0x18000d1c9  lea     r8d, [rdx+6Ch]; Size
0x18000d1cd  call    memset_0
0x18000d1d2  mov     rax, [rbx+28h]
0x18000d1d6  mov     rcx, [rbx+68h]
0x18000d1da  mov     [rbp+57h+pExecInfo.lpFile], rax
0x18000d1de  mov     eax, 800000h
0x18000d1e3  mov     [rbp+57h+pExecInfo.lpVerb], rdi
0x18000d1e7  mov     [rbp+57h+pExecInfo.hwnd], r14
0x18000d1eb  mov     [rbp+57h+pExecInfo.nShow], 1
0x18000d1f2  test    rcx, rcx
0x18000d1f5  jz      short loc_18000D200
0x18000d1f7  mov     [rbp+57h+pExecInfo.hkeyClass], rcx
0x18000d1fb  mov     eax, 800003h
0x18000d200  test    rsi, rsi
0x18000d203  jz      short loc_18000D20C
0x18000d205  or      eax, 140h
0x18000d20a  jmp     short loc_18000D210
0x18000d20c  bts     eax, 14h
0x18000d210  lea     rcx, [rbp+57h+pExecInfo]; pExecInfo
0x18000d214  mov     [rbp+57h+pExecInfo.fMask], eax
0x18000d217  call    cs:__imp_ShellExecuteExW
0x18000d21d  test    eax, eax
0x18000d21f  jz      short loc_18000D225
0x18000d221  xor     edi, edi
0x18000d223  jmp     short loc_18000D230
0x18000d225  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18000d22a  mov     edi, eax
0x18000d22c  test    eax, eax
0x18000d22e  js      short loc_18000D249
0x18000d230  mov     rcx, [rbp+57h+pExecInfo.hProcess]; hObject
0x18000d234  test    rsi, rsi
0x18000d237  jz      short loc_18000D23E
0x18000d239  mov     [rsi], rcx
0x18000d23c  jmp     short loc_18000D249
0x18000d23e  test    rcx, rcx
0x18000d241  jz      short loc_18000D249
0x18000d243  call    cs:__imp_CloseHandle
0x18000d249  mov     r8d, 1
0x18000d24f  mov     edx, edi
0x18000d251  mov     rcx, rbx
0x18000d254  jmp     short loc_18000D25E
0x18000d256  xor     r8d, r8d
0x18000d259  mov     edx, 80070057h
0x18000d25e  call    ?ReportResult@CAttachmentServices@@AEAAHJW4OP_RESULT@1@@Z; CAttachmentServices::ReportResult(long,CAttachmentServices::OP_RESULT)
0x18000d263  mov     edx, [rbp+57h+var_A0]
0x18000d266  mov     rcx, rbx
0x18000d269  call    ?PopOp@CAttachmentServices@@AEAAXW4ATTACHMENT_OP@@@Z; CAttachmentServices::PopOp(ATTACHMENT_OP)
0x18000d26e  mov     rdx, r14; hWndParent
0x18000d271  mov     rcx, rbx; this
0x18000d274  add     rsp, 0A0h
0x18000d27b  pop     r14
0x18000d27d  pop     rdi
0x18000d27e  pop     rsi
0x18000d27f  pop     rbx
0x18000d280  pop     rbp
0x18000d281  jmp     ?DetailedResult@CAttachmentServices@@AEAAJPEAUHWND__@@@Z; CAttachmentServices::DetailedResult(HWND__ *)
```
