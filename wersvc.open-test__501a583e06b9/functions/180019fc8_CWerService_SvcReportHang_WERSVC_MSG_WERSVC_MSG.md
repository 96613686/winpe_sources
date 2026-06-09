# CWerService::SvcReportHang(_WERSVC_MSG *,_WERSVC_MSG *)

- ea: `0x180019fc8`
- end: `0x18001a31d`
- name: `?SvcReportHang@CWerService@@AEAAJPEAU_WERSVC_MSG@@0@Z`
- size: `853`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, struct _WERSVC_MSG *, struct _WERSVC_MSG *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014fa4`

## callees

- `0x180006a80`
- `0x180011ef8`
- `0x1800157b4`
- `0x18001672c`
- `0x180019fc8`
- `0x18001b0b4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a111`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a126`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a2f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a309`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a111`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a126`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a2f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a309`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWerService::SvcReportHang(
        struct _RTL_CRITICAL_SECTION *this,
        struct _WERSVC_MSG *a2,
        struct _WERSVC_MSG *a3)
{
  int v6; // ebx
  CWerService *v7; // rcx
  HANDLE *v8; // rcx
  int v10; // eax
  void *v11; // rcx
  HANDLE hObject; // [rsp+88h] [rbp+1Fh] BYREF
  __int64 v13; // [rsp+90h] [rbp+27h] BYREF
  HANDLE v14; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v15; // [rsp+E8h] [rbp+7Fh] BYREF

  hObject = 0;
  *((_DWORD *)a3 + 10) = 1;
  *((_DWORD *)a3 + 11) = -2147467259;
  v6 = CWerService::OpenSenderProcessThread(this, 0x1FFFFF, (__int64)&hObject, 1);
  if ( v6 != -2147020644 )
    goto LABEL_19;
  if ( (*((_DWORD *)a2 + 344) & 0x20000) == 0 )
    goto LABEL_6;
  v6 = CWerService::OpenSenderProcessThread(this, 0x1FFFFF, (__int64)&hObject, 0);
  if ( v6 >= 0 )
  {
    if ( !CWerService::IsAppContainerHangValid(v7, 0, (unsigned int *)a2 + 12) )
    {
      v6 = -2147020579;
LABEL_6:
      v8 = (HANDLE *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_10:
        if ( v6 != -2145681404 )
        {
          if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
            WPP_SF_d(v8[2], 109, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, (unsigned int)v6);
          *((_DWORD *)a3 + 10) = 268435458;
          *((_DWORD *)a3 + 11) = v6;
        }
        goto LABEL_15;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        108,
        WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
        (unsigned int)v6);
LABEL_9:
      v8 = (HANDLE *)WPP_GLOBAL_Control;
      goto LABEL_10;
    }
  }
  else
  {
LABEL_19:
    if ( v6 == -2147024891 || v6 == -805306334 )
      v6 = CWerService::OpenSenderProcessThread(this, 0, 0, 2);
    if ( v6 < 0 )
      goto LABEL_6;
  }
  v13 = 0;
  v14 = 0;
  v15 = 0;
  *((_WORD *)a2 + 427) = 0;
  *((_WORD *)a2 + 687) = 0;
  v10 = CWerService::TryReportHang(
          (int)this,
          0,
          (int)hObject,
          (int)a2 + 48,
          *((_DWORD *)a2 + 28),
          (unsigned __int64 *)a2 + 15,
          (unsigned __int8 *)a2 + 248,
          (int *)a2 + 66,
          *((HWND *)a2 + 41),
          (__int64)a2 + 336,
          *((_DWORD *)a2 + 344),
          (__int64)a2 + 856,
          *((_DWORD *)a2 + 345),
          (__int64)&v13,
          (__int64)&v14,
          (__int64)&v15);
  v6 = v10;
  if ( v10 == 1 || v10 == -2145681404 )
  {
    *((_DWORD *)a3 + 10) = 268435461;
    *((_QWORD *)a3 + 173) = v14;
    *((_QWORD *)a3 + 174) = v15;
    *((_QWORD *)a3 + 6) = v13;
  }
  else
  {
    if ( v10 == 1769483 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
      *((_DWORD *)a3 + 10) = 268435458;
      *((_QWORD *)a3 + 173) = 0;
      *((_QWORD *)a3 + 174) = 0;
      *((_DWORD *)a3 + 11) = -2147023604;
      goto LABEL_29;
    }
    if ( v10 < 0 )
    {
LABEL_29:
      v11 = (void *)v15;
      goto LABEL_34;
    }
    *((_QWORD *)a3 + 5) = 268435457;
    *((_QWORD *)a3 + 173) = v14;
    *((_QWORD *)a3 + 174) = v15;
  }
  v11 = 0;
  v14 = 0;
LABEL_34:
  if ( (unsigned __int64)v11 + 1 > 1 )
    CloseHandle(v11);
  if ( (unsigned __int64)v14 + 1 > 1 )
    CloseHandle(v14);
  if ( v6 < 0 )
    goto LABEL_9;
LABEL_15:
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180019fc8  mov     [rsp-8+arg_0], rbx
0x180019fcd  mov     [rsp-8+arg_8], rsi
0x180019fd2  push    rbp
0x180019fd3  push    rdi
0x180019fd4  push    r12
0x180019fd6  push    r14
0x180019fd8  push    r15
0x180019fda  lea     rbp, [rsp-37h]
0x180019fdf  sub     rsp, 0A0h
0x180019fe6  mov     rsi, r8
0x180019fe9  mov     r14, rdx
0x180019fec  mov     r15, rcx
0x180019fef  xor     r12d, r12d
0x180019ff2  mov     [rbp+57h+var_40], r12
0x180019ff6  mov     [rbp+57h+hObject], r12
0x180019ffa  mov     dword ptr [r8+28h], 1
0x18001a002  mov     dword ptr [r8+2Ch], 80004005h
0x18001a00a  mov     dword ptr [rsp+0C0h+var_90], 1; int
0x18001a012  lea     rax, [rbp+57h+hObject]
0x18001a016  mov     [rsp+0C0h+var_98], rax; __int64
0x18001a01b  mov     eax, 1FFFFFh
0x18001a020  mov     [rsp+0C0h+var_A0], eax; int
0x18001a024  lea     r9, [rbp+57h+var_40]
0x18001a028  mov     r8d, eax
0x18001a02b  call    ?OpenSenderProcessThread@CWerService@@AEAAJPEAU_WERSVC_MSG@@KPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@K1K@Z; CWerService::OpenSenderProcessThread(_WERSVC_MSG *,ulong,tlx::unique_any<tlx::file_handle_traits> *,ulong,tlx::unique_any<tlx::file_handle_traits> *,ulong)
0x18001a030  mov     ebx, eax
0x18001a032  cmp     eax, 8007109Ch
0x18001a037  jnz     loc_18001A14A
0x18001a03d  test    dword ptr [r14+560h], 20000h
0x18001a048  jz      short loc_18001A096
0x18001a04a  mov     dword ptr [rsp+0C0h+var_90], r12d; int
0x18001a04f  lea     rax, [rbp+57h+hObject]
0x18001a053  mov     [rsp+0C0h+var_98], rax; __int64
0x18001a058  mov     r8d, 1FFFFFh
0x18001a05e  mov     [rsp+0C0h+var_A0], r8d; int
0x18001a063  lea     r9, [rbp+57h+var_40]
0x18001a067  mov     rdx, r14
0x18001a06a  mov     rcx, r15; lpCriticalSection
0x18001a06d  call    ?OpenSenderProcessThread@CWerService@@AEAAJPEAU_WERSVC_MSG@@KPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@K1K@Z; CWerService::OpenSenderProcessThread(_WERSVC_MSG *,ulong,tlx::unique_any<tlx::file_handle_traits> *,ulong,tlx::unique_any<tlx::file_handle_traits> *,ulong)
0x18001a072  mov     ebx, eax
0x18001a074  test    eax, eax
0x18001a076  js      loc_18001A14A
0x18001a07c  lea     r8, [r14+30h]; unsigned int *
0x18001a080  mov     rdx, [rbp+57h+var_40]; void *
0x18001a084  call    ?IsAppContainerHangValid@CWerService@@AEAA_NPEAXPEAK@Z; CWerService::IsAppContainerHangValid(void *,ulong *)
0x18001a089  test    al, al
0x18001a08b  jnz     loc_18001A187
0x18001a091  mov     ebx, 800710DDh
0x18001a096  lea     rdi, WPP_GLOBAL_Control
0x18001a09d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a0a4  cmp     rcx, rdi
0x18001a0a7  jz      short loc_18001A0CE
0x18001a0a9  test    byte ptr [rcx+1Ch], 1
0x18001a0ad  jz      short loc_18001A0CE
0x18001a0af  mov     edx, 6Ch ; 'l'
0x18001a0b4  mov     r9d, ebx
0x18001a0b7  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001a0be  mov     rcx, [rcx+10h]
0x18001a0c2  call    WPP_SF_d
0x18001a0c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a0ce  cmp     ebx, 801B8004h
0x18001a0d4  jz      short loc_18001A103
0x18001a0d6  cmp     rcx, rdi
0x18001a0d9  jz      short loc_18001A0F9
0x18001a0db  test    byte ptr [rcx+1Ch], 1
0x18001a0df  jz      short loc_18001A0F9
0x18001a0e1  mov     edx, 6Dh ; 'm'
0x18001a0e6  mov     r9d, ebx
0x18001a0e9  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001a0f0  mov     rcx, [rcx+10h]
0x18001a0f4  call    WPP_SF_d
0x18001a0f9  mov     dword ptr [rsi+28h], 10000002h
0x18001a100  mov     [rsi+2Ch], ebx
0x18001a103  mov     rcx, [rbp+57h+hObject]; hObject
0x18001a107  lea     rax, [rcx+1]
0x18001a10b  cmp     rax, 1
0x18001a10f  jbe     short loc_18001A118
0x18001a111  call    cs:__imp_CloseHandle
0x18001a117  nop
0x18001a118  mov     rcx, [rbp+57h+var_40]; hObject
0x18001a11c  lea     rax, [rcx+1]
0x18001a120  cmp     rax, 1
0x18001a124  jbe     short loc_18001A12C
0x18001a126  call    cs:__imp_CloseHandle
0x18001a12c  mov     eax, ebx
0x18001a12e  lea     r11, [rsp+0C0h+var_20]
0x18001a136  mov     rbx, [r11+30h]
0x18001a13a  mov     rsi, [r11+38h]
0x18001a13e  mov     rsp, r11
0x18001a141  pop     r15
0x18001a143  pop     r14
0x18001a145  pop     r12
0x18001a147  pop     rdi
0x18001a148  pop     rbp
0x18001a149  retn
0x18001a14a  cmp     ebx, 80070005h
0x18001a150  jz      short loc_18001A15A
0x18001a152  cmp     ebx, 0D0000022h
0x18001a158  jnz     short loc_18001A17F
0x18001a15a  mov     dword ptr [rsp+0C0h+var_90], 2; int
0x18001a162  mov     [rsp+0C0h+var_98], r12; __int64
0x18001a167  mov     [rsp+0C0h+var_A0], r12d; int
0x18001a16c  xor     r9d, r9d
0x18001a16f  xor     r8d, r8d
0x18001a172  mov     rdx, r14
0x18001a175  mov     rcx, r15; lpCriticalSection
0x18001a178  call    ?OpenSenderProcessThread@CWerService@@AEAAJPEAU_WERSVC_MSG@@KPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@K1K@Z; CWerService::OpenSenderProcessThread(_WERSVC_MSG *,ulong,tlx::unique_any<tlx::file_handle_traits> *,ulong,tlx::unique_any<tlx::file_handle_traits> *,ulong)
0x18001a17d  mov     ebx, eax
0x18001a17f  test    ebx, ebx
0x18001a181  js      loc_18001A096
0x18001a187  mov     [rbp+57h+var_30], r12
0x18001a18b  mov     [rbp+57h+arg_10], r12
0x18001a18f  mov     [rbp+57h+arg_18], r12
0x18001a193  mov     [r14+356h], r12w
0x18001a19b  mov     [r14+55Eh], r12w
0x18001a1a3  lea     r9, [r14+30h]; int
0x18001a1a7  lea     rcx, [r14+358h]
0x18001a1ae  lea     r10, [r14+150h]
0x18001a1b5  lea     r11, [r14+108h]
0x18001a1bc  lea     rbx, [r14+0F8h]
0x18001a1c3  lea     rdi, [r14+78h]
0x18001a1c7  lea     rax, [rbp+57h+arg_18]
0x18001a1cb  mov     [rsp+0C0h+var_48], rax; __int64
0x18001a1d0  lea     rax, [rbp+57h+arg_10]
0x18001a1d4  mov     [rsp+0C0h+var_50], rax; __int64
0x18001a1d9  lea     rax, [rbp+57h+var_30]
0x18001a1dd  mov     [rsp+0C0h+var_58], rax; __int64
0x18001a1e2  mov     eax, [r9+534h]
0x18001a1e9  mov     [rsp+0C0h+var_60], eax; unsigned int
0x18001a1ed  mov     [rsp+0C0h+var_68], rcx; __int64
0x18001a1f2  mov     eax, [r14+560h]
0x18001a1f9  mov     [rsp+0C0h+var_70], eax; unsigned int
0x18001a1fd  mov     [rsp+0C0h+var_78], r10; __int64
0x18001a202  mov     rax, [r14+148h]
0x18001a209  mov     [rsp+0C0h+var_80], rax; HWND
0x18001a20e  mov     [rsp+0C0h+var_88], r11; int *
0x18001a213  mov     [rsp+0C0h+var_90], rbx; unsigned __int8 *
0x18001a218  mov     [rsp+0C0h+var_98], rdi; unsigned __int64 *
0x18001a21d  mov     eax, [r14+70h]
0x18001a221  mov     [rsp+0C0h+var_A0], eax; int
0x18001a225  mov     r8, [rbp+57h+hObject]; int
0x18001a229  mov     rdx, [rbp+57h+var_40]; int
0x18001a22d  mov     rcx, r15; int
0x18001a230  call    ?TryReportHang@CWerService@@AEAAJPEAX0PEAKKPEA_KPEAEPEAJPEAUHWND__@@PEA_WKPEB_WKPEAPEAU2@PEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@9@Z; CWerService::TryReportHang(void *,void *,ulong *,ulong,unsigned __int64 *,uchar *,long *,HWND__ *,wchar_t *,ulong,wchar_t const *,ulong,HWND__ * *,tlx::unique_any<tlx::file_handle_traits> *,tlx::unique_any<tlx::file_handle_traits> *)
0x18001a235  mov     ebx, eax
0x18001a237  lea     rdi, WPP_GLOBAL_Control
0x18001a23e  cmp     eax, 1
0x18001a241  jz      short loc_18001A2BE
0x18001a243  cmp     eax, 801B8004h
0x18001a248  jz      short loc_18001A2BE
0x18001a24a  cmp     eax, 1B000Bh
0x18001a24f  jnz     short loc_18001A29A
0x18001a251  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a258  cmp     rcx, rdi
0x18001a25b  jz      short loc_18001A278
0x18001a25d  test    byte ptr [rcx+1Ch], 4
0x18001a261  jz      short loc_18001A278
0x18001a263  mov     edx, 6Bh ; 'k'
0x18001a268  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001a26f  mov     rcx, [rcx+10h]
0x18001a273  call    WPP_SF_
0x18001a278  mov     dword ptr [rsi+28h], 10000002h
0x18001a27f  mov     [rsi+568h], r12
0x18001a286  mov     [rsi+570h], r12
0x18001a28d  mov     dword ptr [rsi+2Ch], 8007050Ch
0x18001a294  mov     rcx, [rbp+57h+arg_18]
0x18001a298  jmp     short loc_18001A2EA
0x18001a29a  test    ebx, ebx
0x18001a29c  js      short loc_18001A294
0x18001a29e  mov     qword ptr [rsi+28h], 10000001h
0x18001a2a6  mov     rax, [rbp+57h+arg_10]
0x18001a2aa  mov     [rsi+568h], rax
0x18001a2b1  mov     rax, [rbp+57h+arg_18]
0x18001a2b5  mov     [rsi+570h], rax
0x18001a2bc  jmp     short loc_18001A2E3
0x18001a2be  mov     dword ptr [rsi+28h], 10000005h
0x18001a2c5  mov     rax, [rbp+57h+arg_10]
0x18001a2c9  mov     [rsi+568h], rax
0x18001a2d0  mov     rax, [rbp+57h+arg_18]
0x18001a2d4  mov     [rsi+570h], rax
0x18001a2db  mov     rax, [rbp+57h+var_30]
0x18001a2df  mov     [rsi+30h], rax
0x18001a2e3  mov     rcx, r12; hObject
0x18001a2e6  mov     [rbp+57h+arg_10], r12
0x18001a2ea  lea     rax, [rcx+1]
0x18001a2ee  cmp     rax, 1
0x18001a2f2  jbe     short loc_18001A2FB
0x18001a2f4  call    cs:__imp_CloseHandle
0x18001a2fa  nop
0x18001a2fb  mov     rcx, [rbp+57h+arg_10]; hObject
0x18001a2ff  lea     rax, [rcx+1]
0x18001a303  cmp     rax, 1
0x18001a307  jbe     short loc_18001A30F
0x18001a309  call    cs:__imp_CloseHandle
0x18001a30f  test    ebx, ebx
0x18001a311  jns     loc_18001A103
0x18001a317  jmp     loc_18001A0C7
```
