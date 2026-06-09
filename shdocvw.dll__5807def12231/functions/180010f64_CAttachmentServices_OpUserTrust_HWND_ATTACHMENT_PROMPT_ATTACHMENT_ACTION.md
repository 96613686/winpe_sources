# CAttachmentServices::_OpUserTrust(HWND__ *,ATTACHMENT_PROMPT,ATTACHMENT_ACTION *)

- ea: `0x180010f64`
- end: `0x1800110c5`
- name: `?_OpUserTrust@CAttachmentServices@@AEAAXPEAUHWND__@@W4ATTACHMENT_PROMPT@@PEAW4ATTACHMENT_ACTION@@@Z`
- size: `353`
- prototype: `void __fastcall(CAttachmentServices *this, HWND, int, enum ATTACHMENT_ACTION *)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18000d110`
- `0x18000f420`

## callees

- `0x180002d10`
- `0x180003080`
- `0x180003f30`
- `0x180004190`
- `0x180006844`
- `0x18000699c`
- `0x180008320`
- `0x180010f64`
- `0x18001d5d8`

## import_xrefs

- `SHLWAPI!__imp_SKSetValueW` at `0x180011078`
- `SHLWAPI!__imp_SKSetValueW` at `0x180011078`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CAttachmentServices::_OpUserTrust(
        CAttachmentServices *this,
        HWND a2,
        int a3,
        enum ATTACHMENT_ACTION *a4)
{
  int v4; // r12d
  __int64 v8; // rcx
  __int64 v9; // rax
  _DWORD *v10; // rax
  bool v11; // zf
  const WCHAR *v12; // rdi
  unsigned __int16 *v13; // rsi
  bool v14; // bl
  int v15; // eax
  enum ATTACHMENT_ACTION v16; // edi
  const unsigned __int16 *Type; // rbx
  int v18; // r8d
  __int64 v19; // rdx
  __int64 v20; // rcx
  int v21; // [rsp+40h] [rbp-278h] BYREF
  unsigned int v22; // [rsp+44h] [rbp-274h] BYREF
  unsigned __int16 v23[264]; // [rsp+50h] [rbp-268h] BYREF

  v4 = (int)a2;
  v22 = 0;
  if ( (unsigned int)CAttachmentServices::PushOp(this, 11, &v22) )
  {
    v9 = *(_QWORD *)(v8 + 72) - *(_QWORD *)&GUID_NULL.Data1;
    v21 = 0;
    if ( !v9 )
      v9 = *(_QWORD *)(v8 + 80) - *(_QWORD *)GUID_NULL.Data4;
    v11 = v9 == 0;
    v10 = (_DWORD *)((char *)this + 88);
    if ( v11 || (v11 = *v10 == 6150) )
    {
      v11 = *v10 == 6150;
      v21 = 1;
    }
    v12 = (const WCHAR *)*((_QWORD *)this + 5);
    v13 = (unsigned __int16 *)*((_QWORD *)this + 6);
    v14 = v11;
    v15 = (unsigned int)CAttachmentServices::_FileName(this);
    v16 = (unsigned int)SafeOpenPromptForAttachment(v4, *((_QWORD *)this + 8), v15, a3, v13, v12, (__int64)&v21, v14);
    if ( v16 <= ATTACHMENT_ACTION_CANCEL )
    {
      v19 = 2147943623LL;
    }
    else
    {
      if ( v21 == 2 )
      {
        Type = CAttachmentServices::_GetType(this);
        if ( _ClientKey((const struct _GUID *)((char *)this + 72), v23, v18) )
          SKSetValueW(17, v23, Type);
      }
      v19 = 0;
    }
    *a4 = v16;
    CAttachmentServices::ReportResult(this, v19, 1);
    CAttachmentServices::PopOp(v20, v22);
  }
}

```

## disassembly

```asm
0x180010f64  push    rbx
0x180010f66  push    rbp
0x180010f67  push    rsi
0x180010f68  push    rdi
0x180010f69  push    r12
0x180010f6b  push    r13
0x180010f6d  push    r14
0x180010f6f  push    r15
0x180010f71  sub     rsp, 278h
0x180010f78  mov     rax, cs:__security_cookie
0x180010f7f  xor     rax, rsp
0x180010f82  mov     [rsp+2B8h+var_58], rax
0x180010f8a  mov     r12, rdx
0x180010f8d  mov     [rsp+2B8h+var_278+4], 0
0x180010f95  mov     r13d, r8d
0x180010f98  mov     edx, 0Bh
0x180010f9d  lea     r8, [rsp+2B8h+var_278+4]
0x180010fa2  mov     r15, r9
0x180010fa5  mov     rbp, rcx
0x180010fa8  call    ?PushOp@CAttachmentServices@@AEAAHW4ATTACHMENT_OP@@PEAW42@@Z; CAttachmentServices::PushOp(ATTACHMENT_OP,ATTACHMENT_OP *)
0x180010fad  test    eax, eax
0x180010faf  jz      loc_1800110A1
0x180010fb5  mov     rax, [rcx+48h]
0x180010fb9  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180010fc0  mov     [rsp+2B8h+var_278], 0
0x180010fc8  jnz     short loc_180010FD5
0x180010fca  mov     rax, [rcx+50h]
0x180010fce  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180010fd5  test    rax, rax
0x180010fd8  mov     ecx, 1806h
0x180010fdd  lea     rax, [rbp+58h]
0x180010fe1  jz      short loc_180010FE7
0x180010fe3  cmp     [rax], ecx
0x180010fe5  jnz     short loc_180010FF1
0x180010fe7  cmp     [rax], ecx
0x180010fe9  mov     [rsp+2B8h+var_278], 1
0x180010ff1  mov     rdi, [rbp+28h]
0x180010ff5  mov     rcx, rbp; this
0x180010ff8  mov     rsi, [rbp+30h]
0x180010ffc  setz    bl
0x180010fff  call    ?_FileName@CAttachmentServices@@AEAAPEBGXZ; CAttachmentServices::_FileName(void)
0x180011004  mov     rdx, [rbp+40h]; int
0x180011008  lea     rcx, [rsp+2B8h+var_278]
0x18001100d  mov     [rsp+2B8h+var_280], bl; bool
0x180011011  mov     r9d, r13d; int
0x180011014  mov     [rsp+2B8h+var_288], rcx; __int64
0x180011019  mov     r8, rax; int
0x18001101c  mov     [rsp+2B8h+var_290], rdi; LPCWSTR
0x180011021  mov     rcx, r12; int
0x180011024  mov     [rsp+2B8h+var_298], rsi; unsigned __int16 *
0x180011029  call    SafeOpenPromptForAttachment
0x18001102e  mov     edi, eax
0x180011030  test    eax, eax
0x180011032  jle     short loc_180011082
0x180011034  cmp     [rsp+2B8h+var_278], 2
0x180011039  jnz     short loc_18001107E
0x18001103b  mov     rcx, rbp; this
0x18001103e  call    ?_GetType@CAttachmentServices@@AEAAPEBGXZ; CAttachmentServices::_GetType(void)
0x180011043  lea     rdx, [rsp+2B8h+var_268]; unsigned __int16 *
0x180011048  mov     rbx, rax
0x18001104b  lea     rcx, [rbp+48h]; struct _GUID *
0x18001104f  call    ?_ClientKey@@YAHAEBU_GUID@@PEAGH@Z; _ClientKey(_GUID const &,ushort *,int)
0x180011054  test    eax, eax
0x180011056  jz      short loc_18001107E
0x180011058  xor     r9d, r9d
0x18001105b  mov     dword ptr [rsp+2B8h+var_290], 0
0x180011063  mov     r8, rbx
0x180011066  mov     [rsp+2B8h+var_298], 0
0x18001106f  lea     rdx, [rsp+2B8h+var_268]
0x180011074  lea     ecx, [r9+11h]
0x180011078  call    cs:__imp_SKSetValueW
0x18001107e  xor     edx, edx
0x180011080  jmp     short loc_180011087
0x180011082  mov     edx, 800704C7h
0x180011087  mov     r8d, 1
0x18001108d  mov     [r15], edi
0x180011090  mov     rcx, rbp
0x180011093  call    ?ReportResult@CAttachmentServices@@AEAAHJW4OP_RESULT@1@@Z; CAttachmentServices::ReportResult(long,CAttachmentServices::OP_RESULT)
0x180011098  mov     edx, [rsp+2B8h+var_278+4]
0x18001109c  call    ?PopOp@CAttachmentServices@@AEAAXW4ATTACHMENT_OP@@@Z; CAttachmentServices::PopOp(ATTACHMENT_OP)
0x1800110a1  mov     rcx, [rsp+2B8h+var_58]
0x1800110a9  xor     rcx, rsp; StackCookie
0x1800110ac  call    __security_check_cookie
0x1800110b1  add     rsp, 278h
0x1800110b8  pop     r15
0x1800110ba  pop     r14
0x1800110bc  pop     r13
0x1800110be  pop     r12
0x1800110c0  pop     rdi
0x1800110c1  pop     rsi
0x1800110c2  pop     rbp
0x1800110c3  pop     rbx
0x1800110c4  retn
```
