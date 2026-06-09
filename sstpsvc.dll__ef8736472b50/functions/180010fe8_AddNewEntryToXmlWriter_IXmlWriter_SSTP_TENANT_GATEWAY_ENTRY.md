# AddNewEntryToXmlWriter(IXmlWriter *,_SSTP_TENANT_GATEWAY_ENTRY *)

- ea: `0x180010fe8`
- end: `0x1800111ed`
- name: `?AddNewEntryToXmlWriter@@YAKPEAUIXmlWriter@@PEAU_SSTP_TENANT_GATEWAY_ENTRY@@@Z`
- size: `517`
- prototype: `unsigned int __fastcall(struct IXmlWriter *, struct _SSTP_TENANT_GATEWAY_ENTRY *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014900`

## callees

- `0x1800089dc`
- `0x180008b90`
- `0x180010fe8`
- `0x18001d1da`
- `0x18001d210`
- `0x18001e010`

## string_xrefs

- `0x18001117a`: `AddNewEntryToXmlWriter: WriteStartElement of IXmlWriter object failed with error %d`
- `0x18001109f`: `AddNewEntryToXmlWriter: WriteString of IXmlWriter object failed with error %d`
- `0x1800110da`: `AddNewEntryToXmlWriter: WriteFullEndElement of IXmlWriter object failed with error %d`

## pseudocode

```c
__int64 __fastcall AddNewEntryToXmlWriter(struct IXmlWriter *a1, struct _SSTP_TENANT_GATEWAY_ENTRY *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // r8
  unsigned int i; // esi
  __int64 result; // rax
  int v9; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v10[2044]; // [rsp+34h] [rbp-CCh] BYREF

  v9 = 0;
  memset_0(v10, 0, sizeof(v10));
  v4 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, const wchar_t *, _QWORD))a1->lpVtbl->WriteStartElement)(
         a1,
         0,
         L"Tenant",
         0);
  v5 = v4;
  if ( v4 )
  {
    if ( (byte_18002E903 & 8) == 0 )
      goto LABEL_21;
    v6 = v4;
    LOWORD(v9) = 0;
LABEL_18:
    FormatRRASErrorString(
      &v9,
      L"AddNewEntryToXmlWriter: WriteStartElement of IXmlWriter object failed with error %d",
      v6);
LABEL_19:
    if ( (byte_18002E903 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v9);
    goto LABEL_21;
  }
  v5 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD))a1->lpVtbl->WriteString)(a1, *((_QWORD *)a2 + 1));
  if ( v5 )
  {
LABEL_5:
    if ( (byte_18002E903 & 8) == 0 )
      goto LABEL_21;
    LOWORD(v9) = 0;
    FormatRRASErrorString(&v9, L"AddNewEntryToXmlWriter: WriteString of IXmlWriter object failed with error %d", v5);
    goto LABEL_19;
  }
  v5 = ((__int64 (__fastcall *)(struct IXmlWriter *))a1->lpVtbl->WriteFullEndElement)(a1);
  if ( v5 )
  {
LABEL_8:
    if ( (byte_18002E903 & 8) == 0 )
      goto LABEL_21;
    LOWORD(v9) = 0;
    FormatRRASErrorString(
      &v9,
      L"AddNewEntryToXmlWriter: WriteFullEndElement of IXmlWriter object failed with error %d",
      v5);
    goto LABEL_19;
  }
  for ( i = 0; i < *((_DWORD *)a2 + 4); ++i )
  {
    v5 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, const wchar_t *, _QWORD))a1->lpVtbl->WriteStartElement)(
           a1,
           0,
           L"Gateway",
           0);
    if ( v5 )
    {
      if ( (byte_18002E903 & 8) == 0 )
        break;
      v6 = v5;
      LOWORD(v9) = 0;
      goto LABEL_18;
    }
    v5 = ((__int64 (__fastcall *)(struct IXmlWriter *, __int64))a1->lpVtbl->WriteString)(
           a1,
           *((_QWORD *)a2 + 3) + 510LL * i);
    if ( v5 )
      goto LABEL_5;
    v5 = ((__int64 (__fastcall *)(struct IXmlWriter *))a1->lpVtbl->WriteFullEndElement)(a1);
    if ( v5 )
      goto LABEL_8;
  }
LABEL_21:
  result = 0;
  if ( (v5 & 0x80000000) != 0 )
  {
    result = (unsigned __int16)v5;
    if ( (v5 & 0x1FFF0000) != 0x70000 )
      return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180010fe8  mov     [rsp-8+arg_10], rbx
0x180010fed  mov     [rsp-8+arg_18], rsi
0x180010ff2  push    rbp
0x180010ff3  push    rdi
0x180010ff4  push    r14
0x180010ff6  lea     rbp, [rsp-740h]
0x180010ffe  sub     rsp, 840h
0x180011005  mov     rax, cs:__security_cookie
0x18001100c  xor     rax, rsp
0x18001100f  mov     [rbp+750h+var_20], rax
0x180011016  mov     r14, rdx
0x180011019  mov     rdi, rcx
0x18001101c  xor     eax, eax
0x18001101e  lea     rcx, [rsp+850h+var_81C]; void *
0x180011023  xor     edx, edx; Val
0x180011025  mov     [rsp+850h+var_820], eax
0x180011029  mov     r8d, 7FCh; Size
0x18001102f  call    memset_0
0x180011034  mov     rax, [rdi]
0x180011037  lea     r8, aTenant; "Tenant"
0x18001103e  xor     r9d, r9d
0x180011041  xor     edx, edx
0x180011043  mov     rcx, rdi
0x180011046  mov     rax, [rax+0D8h]
0x18001104d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011052  mov     ebx, eax
0x180011054  test    eax, eax
0x180011056  jz      short loc_180011074
0x180011058  test    cs:byte_18002E903, 8
0x18001105f  jz      loc_1800111AC
0x180011065  xor     ecx, ecx
0x180011067  mov     r8d, eax
0x18001106a  mov     word ptr [rsp+850h+var_820], cx
0x18001106f  jmp     loc_18001117A
0x180011074  mov     rax, [rdi]
0x180011077  mov     rcx, rdi
0x18001107a  mov     rdx, [r14+8]
0x18001107e  mov     rax, [rax+0E0h]
0x180011085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001108a  mov     ebx, eax
0x18001108c  test    eax, eax
0x18001108e  jz      short loc_1800110B3
0x180011090  test    cs:byte_18002E903, 8
0x180011097  jz      loc_1800111AC
0x18001109d  xor     eax, eax
0x18001109f  lea     rdx, aAddnewentrytox_1; "AddNewEntryToXmlWriter: WriteString of "...
0x1800110a6  mov     word ptr [rsp+850h+var_820], ax
0x1800110ab  mov     r8d, ebx
0x1800110ae  jmp     loc_180011181
0x1800110b3  mov     rax, [rdi]
0x1800110b6  mov     rcx, rdi
0x1800110b9  mov     rax, [rax+88h]
0x1800110c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110c5  mov     ebx, eax
0x1800110c7  test    eax, eax
0x1800110c9  jz      short loc_1800110EE
0x1800110cb  test    cs:byte_18002E903, 8
0x1800110d2  jz      loc_1800111AC
0x1800110d8  xor     eax, eax
0x1800110da  lea     rdx, aAddnewentrytox_0; "AddNewEntryToXmlWriter: WriteFullEndEle"...
0x1800110e1  mov     word ptr [rsp+850h+var_820], ax
0x1800110e6  mov     r8d, ebx
0x1800110e9  jmp     loc_180011181
0x1800110ee  xor     esi, esi
0x1800110f0  cmp     esi, [r14+10h]
0x1800110f4  jnb     loc_1800111AC
0x1800110fa  mov     rax, [rdi]
0x1800110fd  lea     r8, aGateway; "Gateway"
0x180011104  xor     r9d, r9d
0x180011107  xor     edx, edx
0x180011109  mov     rcx, rdi
0x18001110c  mov     rax, [rax+0D8h]
0x180011113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011118  mov     ebx, eax
0x18001111a  test    eax, eax
0x18001111c  jnz     short loc_180011167
0x18001111e  mov     rcx, [rdi]
0x180011121  mov     eax, esi
0x180011123  imul    rdx, rax, 1FEh
0x18001112a  mov     rax, [rcx+0E0h]
0x180011131  mov     rcx, rdi
0x180011134  add     rdx, [r14+18h]
0x180011138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001113d  mov     ebx, eax
0x18001113f  test    eax, eax
0x180011141  jnz     loc_180011090
0x180011147  mov     rax, [rdi]
0x18001114a  mov     rcx, rdi
0x18001114d  mov     rax, [rax+88h]
0x180011154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011159  mov     ebx, eax
0x18001115b  test    eax, eax
0x18001115d  jnz     loc_1800110CB
0x180011163  inc     esi
0x180011165  jmp     short loc_1800110F0
0x180011167  test    cs:byte_18002E903, 8
0x18001116e  jz      short loc_1800111AC
0x180011170  xor     eax, eax
0x180011172  mov     r8d, ebx
0x180011175  mov     word ptr [rsp+850h+var_820], ax
0x18001117a  lea     rdx, aAddnewentrytox; "AddNewEntryToXmlWriter: WriteStartEleme"...
0x180011181  lea     rcx, [rsp+850h+var_820]
0x180011186  call    FormatRRASErrorString
0x18001118b  test    cs:byte_18002E903, 8
0x180011192  jz      short loc_1800111AC
0x180011194  lea     r8, [rsp+850h+var_820]
0x180011199  lea     rdx, RasSSTPSvcTraceError
0x1800111a0  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800111a7  call    McTemplateU0z_EventWriteTransfer
0x1800111ac  xor     eax, eax
0x1800111ae  test    ebx, ebx
0x1800111b0  jns     short loc_1800111C5
0x1800111b2  mov     eax, ebx
0x1800111b4  and     eax, 1FFF0000h
0x1800111b9  cmp     eax, 70000h
0x1800111be  movzx   eax, bx
0x1800111c1  jz      short loc_1800111C5
0x1800111c3  mov     eax, ebx
0x1800111c5  mov     rcx, [rbp+750h+var_20]
0x1800111cc  xor     rcx, rsp; StackCookie
0x1800111cf  call    __security_check_cookie
0x1800111d4  lea     r11, [rsp+850h+var_10]
0x1800111dc  mov     rbx, [r11+30h]
0x1800111e0  mov     rsi, [r11+38h]
0x1800111e4  mov     rsp, r11
0x1800111e7  pop     r14
0x1800111e9  pop     rdi
0x1800111ea  pop     rbp
0x1800111eb  retn
```
