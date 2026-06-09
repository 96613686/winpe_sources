# CAttachmentServices::Prompt(HWND__ *,ATTACHMENT_PROMPT,ATTACHMENT_ACTION *)

- ea: `0x18000f420`
- end: `0x18000f508`
- name: `?Prompt@CAttachmentServices@@UEAAJPEAUHWND__@@W4ATTACHMENT_PROMPT@@PEAW4ATTACHMENT_ACTION@@@Z`
- size: `232`
- prototype: `__int64 __fastcall(LPARAM this, HWND hWndParent, enum ATTACHMENT_PROMPT, enum ATTACHMENT_ACTION *)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, service_task`

## callees

- `0x180002d10`
- `0x180003080`
- `0x180003f30`
- `0x180004340`
- `0x18000cf8c`
- `0x18000f388`
- `0x18000f420`
- `0x180010dbc`
- `0x180010e3c`
- `0x180010f64`
- `0x1800110cc`
- `0x180011148`

## import_xrefs

- `USER32!IsWindow` at `0x18000f45f`
- `USER32!IsWindow` at `0x18000f45f`

## pseudocode

```c
__int64 __fastcall CAttachmentServices::Prompt(
        LPARAM this,
        HWND hWndParent,
        enum ATTACHMENT_ACTION a3,
        enum ATTACHMENT_ACTION *a4)
{
  __int64 v8; // rcx
  CAttachmentServices *v9; // rcx
  int v11; // [rsp+68h] [rbp+20h] BYREF

  *a4 = ATTACHMENT_ACTION_CANCEL;
  v11 = 0;
  if ( (unsigned int)CAttachmentServices::PushOp(this, 3, &v11) )
  {
    if ( IsWindow(hWndParent) && (unsigned int)(a3 - 1) <= 2 )
    {
      CAttachmentServices::_OpStaticFileTypeTrust((CAttachmentServices *)this);
      if ( *(_QWORD *)(this + 40) )
      {
        CAttachmentServices::_OpValidateLocalPath((CAttachmentServices *)this);
        CAttachmentServices::_OpTrustedHandler((CAttachmentServices *)this);
      }
      CAttachmentServices::_OpZoneCheck((CAttachmentServices *)this);
      if ( (unsigned int)CAttachmentServices::Continuable((CAttachmentServices *)this) )
      {
        if ( ((*(_DWORD *)(this + 284) - 2) & 0xFFFFFFFD) != 0 || a3 == (ATTACHMENT_ACTION_EXEC|ATTACHMENT_ACTION_SAVE) )
        {
          CAttachmentServices::OpReset(v8, 11);
          CAttachmentServices::_OpUserTrust(v9, hWndParent, a3, a4);
        }
        else
        {
          *a4 = a3;
        }
      }
    }
    else
    {
      CAttachmentServices::ReportResult(this, 2147942487LL, 0);
    }
    CAttachmentServices::PopOp((int *)this, v11);
  }
  return CAttachmentServices::DetailedResult((CAttachmentServices *)this, hWndParent);
}

```

## disassembly

```asm
0x18000f420  push    rbx
0x18000f422  push    rsi
0x18000f423  push    rdi
0x18000f424  push    r14
0x18000f426  sub     rsp, 28h
0x18000f42a  mov     rsi, rdx
0x18000f42d  mov     dword ptr [r9], 0
0x18000f434  mov     edi, r8d
0x18000f437  mov     [rsp+48h+arg_18], 0
0x18000f43f  lea     r8, [rsp+48h+arg_18]
0x18000f444  mov     edx, 3
0x18000f449  mov     r14, r9
0x18000f44c  mov     rbx, rcx
0x18000f44f  call    ?PushOp@CAttachmentServices@@AEAAHW4ATTACHMENT_OP@@PEAW42@@Z; CAttachmentServices::PushOp(ATTACHMENT_OP,ATTACHMENT_OP *)
0x18000f454  test    eax, eax
0x18000f456  jz      loc_18000F4F4
0x18000f45c  mov     rcx, rsi; hWnd
0x18000f45f  call    cs:__imp_IsWindow
0x18000f465  test    eax, eax
0x18000f467  jz      short loc_18000F4D8
0x18000f469  lea     eax, [rdi-1]
0x18000f46c  cmp     eax, 2
0x18000f46f  ja      short loc_18000F4D8
0x18000f471  mov     rcx, rbx; this
0x18000f474  call    ?_OpStaticFileTypeTrust@CAttachmentServices@@AEAAXXZ; CAttachmentServices::_OpStaticFileTypeTrust(void)
0x18000f479  cmp     qword ptr [rbx+28h], 0
0x18000f47e  jz      short loc_18000F490
0x18000f480  mov     rcx, rbx; this
0x18000f483  call    ?_OpValidateLocalPath@CAttachmentServices@@AEAAXXZ; CAttachmentServices::_OpValidateLocalPath(void)
0x18000f488  mov     rcx, rbx; this
0x18000f48b  call    ?_OpTrustedHandler@CAttachmentServices@@AEAAXXZ; CAttachmentServices::_OpTrustedHandler(void)
0x18000f490  mov     rcx, rbx; this
0x18000f493  call    ?_OpZoneCheck@CAttachmentServices@@AEAAXXZ; CAttachmentServices::_OpZoneCheck(void)
0x18000f498  mov     rcx, rbx; this
0x18000f49b  call    ?Continuable@CAttachmentServices@@AEAAHXZ; CAttachmentServices::Continuable(void)
0x18000f4a0  test    eax, eax
0x18000f4a2  jz      short loc_18000F4E8
0x18000f4a4  mov     eax, [rbx+11Ch]
0x18000f4aa  sub     eax, 2
0x18000f4ad  test    eax, 0FFFFFFFDh
0x18000f4b2  jnz     short loc_18000F4BE
0x18000f4b4  cmp     edi, 3
0x18000f4b7  jz      short loc_18000F4BE
0x18000f4b9  mov     [r14], edi
0x18000f4bc  jmp     short loc_18000F4E8
0x18000f4be  mov     edx, 0Bh
0x18000f4c3  call    ?OpReset@CAttachmentServices@@AEAAXW4ATTACHMENT_OP@@@Z; CAttachmentServices::OpReset(ATTACHMENT_OP)
0x18000f4c8  mov     r8d, edi; enum ATTACHMENT_PROMPT
0x18000f4cb  mov     r9, r14; enum ATTACHMENT_ACTION *
0x18000f4ce  mov     rdx, rsi; HWND
0x18000f4d1  call    ?_OpUserTrust@CAttachmentServices@@AEAAXPEAUHWND__@@W4ATTACHMENT_PROMPT@@PEAW4ATTACHMENT_ACTION@@@Z; CAttachmentServices::_OpUserTrust(HWND__ *,ATTACHMENT_PROMPT,ATTACHMENT_ACTION *)
0x18000f4d6  jmp     short loc_18000F4E8
0x18000f4d8  xor     r8d, r8d
0x18000f4db  mov     edx, 80070057h
0x18000f4e0  mov     rcx, rbx
0x18000f4e3  call    ?ReportResult@CAttachmentServices@@AEAAHJW4OP_RESULT@1@@Z; CAttachmentServices::ReportResult(long,CAttachmentServices::OP_RESULT)
0x18000f4e8  mov     edx, [rsp+48h+arg_18]
0x18000f4ec  mov     rcx, rbx
0x18000f4ef  call    ?PopOp@CAttachmentServices@@AEAAXW4ATTACHMENT_OP@@@Z; CAttachmentServices::PopOp(ATTACHMENT_OP)
0x18000f4f4  mov     rdx, rsi; hWndParent
0x18000f4f7  mov     rcx, rbx; this
0x18000f4fa  add     rsp, 28h
0x18000f4fe  pop     r14
0x18000f500  pop     rdi
0x18000f501  pop     rsi
0x18000f502  pop     rbx
0x18000f503  jmp     ?DetailedResult@CAttachmentServices@@AEAAJPEAUHWND__@@@Z; CAttachmentServices::DetailedResult(HWND__ *)
```
