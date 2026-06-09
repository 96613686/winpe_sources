# CTptControlPacket::GetClientAt(ushort const *,ulong,_WDSTPT_CLIENT *)

- ea: `0x18001cb58`
- end: `0x18001ce85`
- name: `?GetClientAt@CTptControlPacket@@QEAAKPEBGKPEAU_WDSTPT_CLIENT@@@Z`
- size: `813`
- prototype: `unsigned int __fastcall(CTptControlPacket *__hidden this, const unsigned __int16 *, unsigned int, struct _WDSTPT_CLIENT *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x18001cab8`

## callees

- `0x18001c8fc`
- `0x18001cb58`
- `0x18001d67c`
- `0x18001e32c`
- `0x18001e428`
- `0x18001e460`
- `0x18001e528`
- `0x18001e5cc`
- `0x18001e6ec`
- `0x18001e76c`
- `0x18001e9c2`

## string_xrefs

- `0x18001ce03`: `UserSid`

## pseudocode

```c
__int64 __fastcall CTptControlPacket::GetClientAt(
        CTptControlPacket *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        struct _WDSTPT_CLIENT *a4)
{
  __int64 HANDLE; // rbx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // r8
  unsigned int ULONG; // eax
  char v23; // bl
  char v24; // dl
  unsigned int v25; // eax
  char v26; // dl
  const unsigned __int16 *v27; // r8
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rdx
  __int64 v31; // r8
  _DWORD *v32; // rbx
  const unsigned __int16 *v33; // rdx
  const unsigned __int16 *v34; // r8
  __int64 v35; // rdx
  __int64 v36; // r8
  size_t Size; // [rsp+28h] [rbp-20h]
  unsigned int v39; // [rsp+58h] [rbp+10h] BYREF
  int v40; // [rsp+5Ch] [rbp+14h]

  v40 = HIDWORD(a2);
  v39 = 0;
  memset_0(a4, 0, 0x860u);
  HANDLE = CControlPacket::GetHANDLE(this, L"CntList", L"NSHandle", a3, (void **)a4);
  if ( (unsigned int)ElValidateWin32_15(HANDLE, v8, v9, 1573) )
    goto LABEL_21;
  HANDLE = CControlPacket::GetHANDLE(this, L"CntList", L"CoHandle", a3, (void **)a4 + 1);
  if ( (unsigned int)ElValidateWin32_15(HANDLE, v10, v11, 1584) )
    goto LABEL_21;
  HANDLE = CControlPacket::GetHANDLE(this, L"CntList", L"SeHandle", a3, (void **)a4 + 2);
  if ( (unsigned int)ElValidateWin32_15(HANDLE, v12, v13, 1595) )
    goto LABEL_21;
  HANDLE = CControlPacket::GetHANDLE(this, L"CntList", L"Handle", a3, (void **)a4 + 3);
  if ( (unsigned int)ElValidateWin32_15(HANDLE, v14, v15, 1606) )
    goto LABEL_21;
  HANDLE = CControlPacket::GetString(this, L"CntList", L"Name", a3, (unsigned __int16 **)a4 + 4);
  if ( (unsigned int)ElValidateWin32_15(HANDLE, v16, v17, 1617) )
    goto LABEL_21;
  HANDLE = CControlPacket::GetULONG(this, L"CntList", L"Progress", a3, (unsigned int *)a4 + 20);
  if ( (unsigned int)ElValidateWin32_15(HANDLE, v18, v19, 1628) )
    goto LABEL_21;
  HANDLE = CControlPacket::GetULONG(this, L"CntList", L"TimeInSe", a3, (unsigned int *)a4 + 21);
  if ( (unsigned int)ElValidateWin32_15(HANDLE, v20, v21, 1639) )
    goto LABEL_21;
  ULONG = CControlPacket::GetULONG(this, L"CntList", L"CPU", a3, &v39);
  v23 = -1;
  v24 = -1;
  if ( !ULONG )
    v24 = v39;
  *((_BYTE *)a4 + 2140) = v24;
  v25 = CControlPacket::GetULONG(this, L"CntList", L"Memory", a3, &v39);
  v26 = -1;
  if ( !v25 )
    v26 = v39;
  *((_BYTE *)a4 + 2141) = v26;
  if ( !CControlPacket::GetULONG(this, L"CntList", L"Network", a3, &v39) )
    v23 = v39;
  *((_BYTE *)a4 + 2142) = v23;
  HANDLE = CControlPacket::GetIPAddress(this, L"CntList", v27, a3, (struct _WDSTPT_CLIENT *)((char *)a4 + 60));
  if ( (unsigned int)ElValidateWin32_15(HANDLE, v28, v29, 1692) )
    goto LABEL_21;
  HANDLE = CControlPacket::GetMacAddress(this, L"CntList", L"MAC", a3, (struct _WDSTPT_CLIENT *)((char *)a4 + 40));
  if ( (unsigned int)ElValidateWin32_15(HANDLE, v30, v31, 1703) )
    goto LABEL_21;
  v32 = (_DWORD *)((char *)a4 + 2136);
  *((_DWORD *)a4 + 534) = 0;
  if ( CControlPacket::GetLength(this, L"CntList", L"UserSid", a3, (unsigned int *)a4 + 534) )
  {
LABEL_20:
    LODWORD(HANDLE) = 0;
    return (unsigned int)HANDLE;
  }
  if ( *v32 <= 0x800u )
  {
    LODWORD(Size) = *v32;
    HANDLE = (unsigned int)CControlPacket::GetBLOB(this, v33, v34, a3, (char *)a4 + 88, Size);
    if ( !(unsigned int)ElValidateWin32_15(HANDLE, v35, v36, 1729) )
      goto LABEL_20;
LABEL_21:
    if ( !(_DWORD)HANDLE )
      return (unsigned int)HANDLE;
    goto LABEL_22;
  }
  LODWORD(HANDLE) = 111;
LABEL_22:
  if ( a4 )
    CTptControlPacket::FreeClient(a4, 0);
  return (unsigned int)HANDLE;
}

```

## disassembly

```asm
0x18001cb58  mov     rax, rsp
0x18001cb5b  mov     [rax+8], rbx
0x18001cb5f  mov     [rax+18h], rbp
0x18001cb63  mov     [rax+10h], rdx
0x18001cb67  push    rsi
0x18001cb68  push    rdi
0x18001cb69  push    r14
0x18001cb6b  sub     rsp, 30h
0x18001cb6f  and     dword ptr [rax+10h], 0
0x18001cb73  mov     esi, r8d
0x18001cb76  mov     rbp, rcx
0x18001cb79  mov     r8d, 860h; Size
0x18001cb7f  mov     rcx, r9; void *
0x18001cb82  xor     edx, edx; Val
0x18001cb84  mov     rdi, r9
0x18001cb87  call    memset_0
0x18001cb8c  lea     r14, aCntlist; "CntList"
0x18001cb93  mov     [rsp+48h+var_28], rdi; void **
0x18001cb98  mov     rdx, r14; unsigned __int16 *
0x18001cb9b  lea     r8, aNshandle; "NSHandle"
0x18001cba2  mov     r9d, esi; unsigned int
0x18001cba5  mov     rcx, rbp; this
0x18001cba8  call    ?GetHANDLE@CControlPacket@@QEAAKPEBG0KPEAPEAX@Z; CControlPacket::GetHANDLE(ushort const *,ushort const *,ulong,void * *)
0x18001cbad  mov     r9d, 625h
0x18001cbb3  mov     ecx, eax
0x18001cbb5  mov     ebx, eax
0x18001cbb7  call    ElValidateWin32_15
0x18001cbbc  test    eax, eax
0x18001cbbe  jnz     loc_18001CE5C
0x18001cbc4  lea     rax, [rdi+8]
0x18001cbc8  mov     r9d, esi; unsigned int
0x18001cbcb  lea     r8, aCohandle; "CoHandle"
0x18001cbd2  mov     [rsp+48h+var_28], rax; void **
0x18001cbd7  mov     rdx, r14; unsigned __int16 *
0x18001cbda  mov     rcx, rbp; this
0x18001cbdd  call    ?GetHANDLE@CControlPacket@@QEAAKPEBG0KPEAPEAX@Z; CControlPacket::GetHANDLE(ushort const *,ushort const *,ulong,void * *)
0x18001cbe2  mov     r9d, 630h
0x18001cbe8  mov     ecx, eax
0x18001cbea  mov     ebx, eax
0x18001cbec  call    ElValidateWin32_15
0x18001cbf1  test    eax, eax
0x18001cbf3  jnz     loc_18001CE5C
0x18001cbf9  lea     rax, [rdi+10h]
0x18001cbfd  mov     r9d, esi; unsigned int
0x18001cc00  lea     r8, aSehandle; "SeHandle"
0x18001cc07  mov     [rsp+48h+var_28], rax; void **
0x18001cc0c  mov     rdx, r14; unsigned __int16 *
0x18001cc0f  mov     rcx, rbp; this
0x18001cc12  call    ?GetHANDLE@CControlPacket@@QEAAKPEBG0KPEAPEAX@Z; CControlPacket::GetHANDLE(ushort const *,ushort const *,ulong,void * *)
0x18001cc17  mov     r9d, 63Bh
0x18001cc1d  mov     ecx, eax
0x18001cc1f  mov     ebx, eax
0x18001cc21  call    ElValidateWin32_15
0x18001cc26  test    eax, eax
0x18001cc28  jnz     loc_18001CE5C
0x18001cc2e  lea     rax, [rdi+18h]
0x18001cc32  mov     r9d, esi; unsigned int
0x18001cc35  lea     r8, aHandle; "Handle"
0x18001cc3c  mov     [rsp+48h+var_28], rax; void **
0x18001cc41  mov     rdx, r14; unsigned __int16 *
0x18001cc44  mov     rcx, rbp; this
0x18001cc47  call    ?GetHANDLE@CControlPacket@@QEAAKPEBG0KPEAPEAX@Z; CControlPacket::GetHANDLE(ushort const *,ushort const *,ulong,void * *)
0x18001cc4c  mov     r9d, 646h
0x18001cc52  mov     ecx, eax
0x18001cc54  mov     ebx, eax
0x18001cc56  call    ElValidateWin32_15
0x18001cc5b  test    eax, eax
0x18001cc5d  jnz     loc_18001CE5C
0x18001cc63  lea     rax, [rdi+20h]
0x18001cc67  mov     r9d, esi; unsigned int
0x18001cc6a  lea     r8, aName; "Name"
0x18001cc71  mov     [rsp+48h+var_28], rax; unsigned __int16 **
0x18001cc76  mov     rdx, r14; unsigned __int16 *
0x18001cc79  mov     rcx, rbp; this
0x18001cc7c  call    ?GetString@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z; CControlPacket::GetString(ushort const *,ushort const *,ulong,ushort * *)
0x18001cc81  mov     r9d, 651h
0x18001cc87  mov     ecx, eax
0x18001cc89  mov     ebx, eax
0x18001cc8b  call    ElValidateWin32_15
0x18001cc90  test    eax, eax
0x18001cc92  jnz     loc_18001CE5C
0x18001cc98  lea     rax, [rdi+50h]
0x18001cc9c  mov     r9d, esi; unsigned int
0x18001cc9f  lea     r8, aProgress; "Progress"
0x18001cca6  mov     [rsp+48h+var_28], rax; unsigned int *
0x18001ccab  mov     rdx, r14; unsigned __int16 *
0x18001ccae  mov     rcx, rbp; this
0x18001ccb1  call    ?GetULONG@CControlPacket@@QEAAKPEBG0KPEAK@Z; CControlPacket::GetULONG(ushort const *,ushort const *,ulong,ulong *)
0x18001ccb6  mov     r9d, 65Ch
0x18001ccbc  mov     ecx, eax
0x18001ccbe  mov     ebx, eax
0x18001ccc0  call    ElValidateWin32_15
0x18001ccc5  test    eax, eax
0x18001ccc7  jnz     loc_18001CE5C
0x18001cccd  lea     rax, [rdi+54h]
0x18001ccd1  mov     r9d, esi; unsigned int
0x18001ccd4  lea     r8, aTimeinse; "TimeInSe"
0x18001ccdb  mov     [rsp+48h+var_28], rax; unsigned int *
0x18001cce0  mov     rdx, r14; unsigned __int16 *
0x18001cce3  mov     rcx, rbp; this
0x18001cce6  call    ?GetULONG@CControlPacket@@QEAAKPEBG0KPEAK@Z; CControlPacket::GetULONG(ushort const *,ushort const *,ulong,ulong *)
0x18001cceb  mov     r9d, 667h
0x18001ccf1  mov     ecx, eax
0x18001ccf3  mov     ebx, eax
0x18001ccf5  call    ElValidateWin32_15
0x18001ccfa  test    eax, eax
0x18001ccfc  jnz     loc_18001CE5C
0x18001cd02  lea     rax, [rsp+48h+arg_8]
0x18001cd07  mov     r9d, esi; unsigned int
0x18001cd0a  lea     r8, aCpu; "CPU"
0x18001cd11  mov     [rsp+48h+var_28], rax; unsigned int *
0x18001cd16  mov     rdx, r14; unsigned __int16 *
0x18001cd19  mov     rcx, rbp; this
0x18001cd1c  call    ?GetULONG@CControlPacket@@QEAAKPEBG0KPEAK@Z; CControlPacket::GetULONG(ushort const *,ushort const *,ulong,ulong *)
0x18001cd21  movzx   ecx, byte ptr [rsp+48h+arg_8]
0x18001cd26  lea     r8, aMemory; "Memory"
0x18001cd2d  test    eax, eax
0x18001cd2f  mov     ebx, 0FFh
0x18001cd34  mov     edx, ebx
0x18001cd36  lea     rax, [rsp+48h+arg_8]
0x18001cd3b  cmovz   edx, ecx
0x18001cd3e  mov     [rsp+48h+var_28], rax; unsigned int *
0x18001cd43  mov     [rdi+85Ch], dl
0x18001cd49  mov     r9d, esi; unsigned int
0x18001cd4c  mov     rdx, r14; unsigned __int16 *
0x18001cd4f  mov     rcx, rbp; this
0x18001cd52  call    ?GetULONG@CControlPacket@@QEAAKPEBG0KPEAK@Z; CControlPacket::GetULONG(ushort const *,ushort const *,ulong,ulong *)
0x18001cd57  movzx   ecx, byte ptr [rsp+48h+arg_8]
0x18001cd5c  lea     r8, aNetwork; "Network"
0x18001cd63  test    eax, eax
0x18001cd65  mov     edx, ebx
0x18001cd67  lea     rax, [rsp+48h+arg_8]
0x18001cd6c  mov     r9d, esi; unsigned int
0x18001cd6f  cmovz   edx, ecx
0x18001cd72  mov     [rsp+48h+var_28], rax; unsigned int *
0x18001cd77  mov     [rdi+85Dh], dl
0x18001cd7d  mov     rcx, rbp; this
0x18001cd80  mov     rdx, r14; unsigned __int16 *
0x18001cd83  call    ?GetULONG@CControlPacket@@QEAAKPEBG0KPEAK@Z; CControlPacket::GetULONG(ushort const *,ushort const *,ulong,ulong *)
0x18001cd88  movzx   ecx, byte ptr [rsp+48h+arg_8]
0x18001cd8d  test    eax, eax
0x18001cd8f  lea     rax, [rdi+3Ch]
0x18001cd93  mov     r9d, esi; unsigned int
0x18001cd96  cmovz   ebx, ecx
0x18001cd99  mov     [rsp+48h+var_28], rax; struct tagWDS_IP_ADDRESS6 *
0x18001cd9e  mov     rcx, rbp; this
0x18001cda1  mov     [rdi+85Eh], bl
0x18001cda7  mov     rdx, r14; unsigned __int16 *
0x18001cdaa  call    ?GetIPAddress@CControlPacket@@QEAAKPEBG0KPEAUtagWDS_IP_ADDRESS6@@@Z; CControlPacket::GetIPAddress(ushort const *,ushort const *,ulong,tagWDS_IP_ADDRESS6 *)
0x18001cdaf  mov     r9d, 69Ch
0x18001cdb5  mov     ecx, eax
0x18001cdb7  mov     ebx, eax
0x18001cdb9  call    ElValidateWin32_15
0x18001cdbe  test    eax, eax
0x18001cdc0  jnz     loc_18001CE5C
0x18001cdc6  lea     rax, [rdi+28h]
0x18001cdca  mov     r9d, esi; unsigned int
0x18001cdcd  lea     r8, aMac; "MAC"
0x18001cdd4  mov     [rsp+48h+var_28], rax; struct tagWDS_MAC_ADDRESS *
0x18001cdd9  mov     rdx, r14; unsigned __int16 *
0x18001cddc  mov     rcx, rbp; this
0x18001cddf  call    ?GetMacAddress@CControlPacket@@QEAAKPEBG0KPEAUtagWDS_MAC_ADDRESS@@@Z; CControlPacket::GetMacAddress(ushort const *,ushort const *,ulong,tagWDS_MAC_ADDRESS *)
0x18001cde4  mov     r9d, 6A7h
0x18001cdea  mov     ecx, eax
0x18001cdec  mov     ebx, eax
0x18001cdee  call    ElValidateWin32_15
0x18001cdf3  test    eax, eax
0x18001cdf5  jnz     short loc_18001CE5C
0x18001cdf7  lea     rbx, [rdi+858h]
0x18001cdfe  mov     r9d, esi; unsigned int
0x18001ce01  and     [rbx], eax
0x18001ce03  lea     r8, aUsersid; "UserSid"
0x18001ce0a  mov     rdx, r14; unsigned __int16 *
0x18001ce0d  mov     [rsp+48h+var_28], rbx; unsigned int *
0x18001ce12  mov     rcx, rbp; this
0x18001ce15  call    ?GetLength@CControlPacket@@QEAAKPEBG0KPEAK@Z; CControlPacket::GetLength(ushort const *,ushort const *,ulong,ulong *)
0x18001ce1a  test    eax, eax
0x18001ce1c  jnz     short loc_18001CE58
0x18001ce1e  mov     ecx, [rbx]
0x18001ce20  cmp     ecx, 800h
0x18001ce26  jbe     short loc_18001CE2D
0x18001ce28  lea     ebx, [rax+6Fh]
0x18001ce2b  jmp     short loc_18001CE60
0x18001ce2d  mov     dword ptr [rsp+48h+Size], ecx; Size
0x18001ce31  lea     rax, [rdi+58h]
0x18001ce35  mov     rcx, rbp; this
0x18001ce38  mov     [rsp+48h+var_28], rax; void *
0x18001ce3d  mov     r9d, esi; unsigned int
0x18001ce40  call    ?GetBLOB@CControlPacket@@QEAAKPEBG0KPEAXK@Z; CControlPacket::GetBLOB(ushort const *,ushort const *,ulong,void *,ulong)
0x18001ce45  mov     r9d, 6C1h
0x18001ce4b  mov     ecx, eax
0x18001ce4d  mov     ebx, eax
0x18001ce4f  call    ElValidateWin32_15
0x18001ce54  test    eax, eax
0x18001ce56  jnz     short loc_18001CE5C
0x18001ce58  xor     ebx, ebx
0x18001ce5a  jmp     short loc_18001CE6F
0x18001ce5c  test    ebx, ebx
0x18001ce5e  jz      short loc_18001CE6F
0x18001ce60  test    rdi, rdi
0x18001ce63  jz      short loc_18001CE6F
0x18001ce65  xor     edx, edx; int
0x18001ce67  mov     rcx, rdi; struct _WDSTPT_CLIENT *
0x18001ce6a  call    ?FreeClient@CTptControlPacket@@SAXPEAU_WDSTPT_CLIENT@@H@Z; CTptControlPacket::FreeClient(_WDSTPT_CLIENT *,int)
0x18001ce6f  mov     rbp, [rsp+48h+arg_10]
0x18001ce74  mov     eax, ebx
0x18001ce76  mov     rbx, [rsp+48h+arg_0]
0x18001ce7b  add     rsp, 30h
0x18001ce7f  pop     r14
0x18001ce81  pop     rdi
0x18001ce82  pop     rsi
0x18001ce83  retn
```
