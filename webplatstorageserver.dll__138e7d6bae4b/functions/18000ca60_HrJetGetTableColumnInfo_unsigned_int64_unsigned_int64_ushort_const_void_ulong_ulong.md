# HrJetGetTableColumnInfo(unsigned __int64,unsigned __int64,ushort const *,void *,ulong,ulong)

- ea: `0x18000ca60`
- end: `0x18000cd30`
- name: `?HrJetGetTableColumnInfo@@YAJ_K0PEBGPEAXKK@Z`
- size: `720`
- prototype: `int(unsigned __int64, unsigned __int64, const unsigned __int16 *, void *, unsigned int, unsigned int)`
- caller_count: `17`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18000bae0`
- `0x18000c920`
- `0x18000deb0`
- `0x18000e3a0`
- `0x18000e780`
- `0x180013c00`
- `0x180048530`
- `0x180048790`
- `0x180048b28`
- `0x180048cf0`
- `0x180048f40`
- `0x180049190`
- `0x180049440`
- `0x18004968c`
- `0x18004a048`
- `0x18004a2a0`
- `0x180067460`

## callees

- `0x18000ca60`
- `0x180037e10`
- `0x18004bd60`
- `0x1800611d0`
- `0x180080fb0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000cba2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ccfc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000cba2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ccfc`
- `ESENT!JetGetTableColumnInfoW` at `0x18000caa3`
- `ESENT!JetGetTableColumnInfoW` at `0x18000caa3`

## pseudocode

```c
__int64 __fastcall HrJetGetTableColumnInfo(
        JET_SESID a1,
        JET_TABLEID a2,
        const unsigned __int16 *a3,
        struct JET_COLUMNDEF *a4)
{
  const WCHAR *v5; // rdi
  JET_ERR TableColumnInfoW; // eax
  unsigned int v9; // ebx
  unsigned __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rax
  int v15; // eax
  unsigned int v17; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v18[3]; // [rsp+34h] [rbp-CCh] BYREF
  JET_TABLEID v19; // [rsp+40h] [rbp-C0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  EVENT_DESCRIPTOR v21; // [rsp+58h] [rbp-A8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+68h] [rbp-98h] BYREF
  char *v23; // [rsp+78h] [rbp-88h]
  int v24; // [rsp+80h] [rbp-80h]
  int v25; // [rsp+84h] [rbp-7Ch]
  unsigned int *v26; // [rsp+88h] [rbp-78h]
  __int64 v27; // [rsp+90h] [rbp-70h]
  struct _EVENT_DATA_DESCRIPTOR v28; // [rsp+A0h] [rbp-60h] BYREF
  __int16 *v29; // [rsp+B0h] [rbp-50h]
  int v30; // [rsp+B8h] [rbp-48h]
  int v31; // [rsp+BCh] [rbp-44h]
  unsigned int *v32; // [rsp+C0h] [rbp-40h]
  __int64 v33; // [rsp+C8h] [rbp-38h]
  EVENT_DESCRIPTOR *p_EventDescriptor; // [rsp+D0h] [rbp-30h]
  __int64 v35; // [rsp+D8h] [rbp-28h]
  JET_TABLEID *v36; // [rsp+E0h] [rbp-20h]
  __int64 v37; // [rsp+E8h] [rbp-18h]
  const WCHAR *v38; // [rsp+F0h] [rbp-10h]
  int v39; // [rsp+F8h] [rbp-8h]
  int v40; // [rsp+FCh] [rbp-4h]
  _DWORD *v41; // [rsp+100h] [rbp+0h]
  __int64 v42; // [rsp+108h] [rbp+8h]

  v5 = a3;
  TableColumnInfoW = JetGetTableColumnInfoW(a1, a2, a3, a4, 0x1Cu, 0);
  if ( !TableColumnInfoW )
    goto LABEL_6;
  if ( TableColumnInfoW >= 0 )
  {
    if ( TableColumnInfoW != 1007 )
    {
      v9 = (unsigned __int16)TableColumnInfoW | 0x8E5E0000;
      goto LABEL_7;
    }
LABEL_6:
    v9 = 0;
    goto LABEL_7;
  }
  v9 = (unsigned __int16)TableColumnInfoW | 0x8E5E0000;
LABEL_7:
  v11 = *((_QWORD *)StorageServerProvider::Instance() + 1);
  if ( *(_DWORD *)v11 > 5u )
  {
    v10 = *(_QWORD *)(v11 + 24);
    if ( (*(_QWORD *)(v11 + 16) & 1) != 0 && (*(_QWORD *)(v11 + 24) & 1LL) == v10 )
    {
      v17 = v9;
      v26 = &v17;
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = *(_QWORD *)(v11 + 8);
      v27 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 1;
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      v23 = byte_1800FA863;
      UserData.Reserved = 2;
      v24 = 39;
      v25 = 1;
      v18[0] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(*(_QWORD *)(v11 + 32), &EventDescriptor, 0, 0, 3u, &UserData);
    }
  }
  if ( StorageServerProvider::IsEnabled(v11, v10) )
  {
    v12 = *((_QWORD *)StorageServerProvider::Instance() + 1);
    if ( *(_DWORD *)v12 > 5u
      && (*(_QWORD *)(v12 + 16) & 1) != 0
      && (*(_QWORD *)(v12 + 24) & 1LL) == *(_QWORD *)(v12 + 24) )
    {
      v18[0] = 0;
      v41 = v18;
      v19 = a2;
      *(_QWORD *)&EventDescriptor.Id = a1;
      v17 = v9;
      v42 = 4;
      if ( v5 )
      {
        v13 = -1;
        while ( v5[++v13] != 0 )
          ;
        v15 = 2 * v13 + 2;
      }
      else
      {
        v5 = &word_1800D6108;
        v15 = 2;
      }
      v39 = v15;
      v38 = v5;
      v36 = &v19;
      v40 = 0;
      p_EventDescriptor = &EventDescriptor;
      v37 = 8;
      v32 = &v17;
      *(_DWORD *)&v21.Level = 5;
      v28.Ptr = *(_QWORD *)(v12 + 8);
      v35 = 8;
      v33 = 4;
      *(_DWORD *)&v21.Id = 184549376;
      v21.Keyword = 1;
      v28.Size = *(unsigned __int16 *)v28.Ptr;
      v29 = word_1800FA80A;
      v28.Reserved = 2;
      v30 = 77;
      v31 = 1;
      v18[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(*(_QWORD *)(v12 + 32), &v21, 0, 0, 7u, &v28);
    }
    if ( !v9 )
      EseTraceLogging::LogColumnDef(a4);
  }
  return v9;
}

```

## disassembly

```asm
0x18000ca60  push    rbp
0x18000ca62  push    rbx
0x18000ca63  push    rsi
0x18000ca64  push    rdi
0x18000ca65  push    r12
0x18000ca67  push    r13
0x18000ca69  push    r14
0x18000ca6b  push    r15
0x18000ca6d  lea     rbp, [rsp-28h]
0x18000ca72  sub     rsp, 128h
0x18000ca79  mov     rax, cs:__security_cookie
0x18000ca80  xor     rax, rsp
0x18000ca83  mov     [rbp+60h+var_50], rax
0x18000ca87  xor     r13d, r13d
0x18000ca8a  mov     r15, r9
0x18000ca8d  mov     [rsp+160h+InfoLevel], r13d; InfoLevel
0x18000ca92  mov     rdi, r8
0x18000ca95  mov     [rsp+160h+cbMax], 1Ch; cbMax
0x18000ca9d  mov     r14, rdx
0x18000caa0  mov     rsi, rcx
0x18000caa3  call    cs:__imp_JetGetTableColumnInfoW
0x18000caa9  test    eax, eax
0x18000caab  jz      short loc_18000CACC
0x18000caad  jns     short loc_18000CABA
0x18000caaf  movzx   ebx, ax
0x18000cab2  or      ebx, 8E5E0000h
0x18000cab8  jmp     short loc_18000CACF
0x18000caba  cmp     eax, 3EFh
0x18000cabf  jz      short loc_18000CACC
0x18000cac1  movzx   ebx, ax
0x18000cac4  or      ebx, 8E5E0000h
0x18000caca  jmp     short loc_18000CACF
0x18000cacc  mov     ebx, r13d
0x18000cacf  call    ?Instance@StorageServerProvider@@KAPEAV1@XZ; StorageServerProvider::Instance(void)
0x18000cad4  lea     r12, _TraceLoggingMetadataEnd
0x18000cadb  lea     r8, _TraceLoggingMetadata
0x18000cae2  mov     rcx, [rax+8]
0x18000cae6  mov     eax, [rcx]
0x18000cae8  cmp     eax, 5
0x18000caeb  jbe     loc_18000CBA8
0x18000caf1  mov     rdx, [rcx+18h]
0x18000caf5  mov     rax, [rcx+10h]
0x18000caf9  test    al, 1
0x18000cafb  jz      loc_18000CBA8
0x18000cb01  mov     rax, rdx
0x18000cb04  and     eax, 1
0x18000cb07  cmp     rax, rdx
0x18000cb0a  jnz     loc_18000CBA8
0x18000cb10  lea     rax, [rsp+160h+var_130]
0x18000cb15  mov     [rsp+160h+var_130], ebx
0x18000cb19  mov     [rbp+60h+var_D8], rax
0x18000cb1d  lea     rdx, [rsp+160h+EventDescriptor]; EventDescriptor
0x18000cb22  movzx   eax, cs:word_1800FA859
0x18000cb29  xor     r9d, r9d; RelatedActivityId
0x18000cb2c  mov     dword ptr [rsp+160h+EventDescriptor.Level], eax
0x18000cb30  mov     rax, [rcx+8]
0x18000cb34  mov     [rsp+160h+UserData.Ptr], rax
0x18000cb39  mov     [rbp+60h+var_D0], 4
0x18000cb41  mov     dword ptr [rsp+160h+EventDescriptor.Id], 0B000000h
0x18000cb49  mov     [rsp+160h+EventDescriptor.Keyword], 1
0x18000cb52  movzx   eax, word ptr [rax]
0x18000cb55  mov     [rsp+160h+UserData.Size], eax
0x18000cb59  lea     rax, byte_1800FA863
0x18000cb60  mov     [rsp+160h+var_E8], rax
0x18000cb65  mov     rax, r12
0x18000cb68  sub     eax, r8d
0x18000cb6b  mov     dword ptr [rsp+160h+UserData.0Ch], 2
0x18000cb73  mov     [rbp+60h+var_E0], 27h ; '''
0x18000cb7a  xor     r8d, r8d; ActivityId
0x18000cb7d  mov     [rbp+60h+var_DC], 1
0x18000cb84  mov     [rsp+160h+var_12C], eax
0x18000cb88  mov     eax, [rsp+160h+var_12C]
0x18000cb8c  mov     rcx, [rcx+20h]; RegHandle
0x18000cb90  lea     rax, [rsp+160h+UserData]
0x18000cb95  mov     qword ptr [rsp+160h+InfoLevel], rax; UserData
0x18000cb9a  mov     [rsp+160h+cbMax], 3; UserDataCount
0x18000cba2  call    cs:__imp_EventWriteTransfer
0x18000cba8  call    ?IsEnabled@StorageServerProvider@@SA_NE_K@Z; StorageServerProvider::IsEnabled(uchar,unsigned __int64)
0x18000cbad  test    al, al
0x18000cbaf  jz      loc_18000CD0E
0x18000cbb5  call    ?Instance@StorageServerProvider@@KAPEAV1@XZ; StorageServerProvider::Instance(void)
0x18000cbba  mov     rcx, [rax+8]
0x18000cbbe  mov     eax, [rcx]
0x18000cbc0  cmp     eax, 5
0x18000cbc3  jbe     loc_18000CD02
0x18000cbc9  mov     rdx, [rcx+18h]
0x18000cbcd  mov     rax, [rcx+10h]
0x18000cbd1  test    al, 1
0x18000cbd3  jz      loc_18000CD02
0x18000cbd9  mov     rax, rdx
0x18000cbdc  and     eax, 1
0x18000cbdf  cmp     rax, rdx
0x18000cbe2  jnz     loc_18000CD02
0x18000cbe8  mov     [rsp+160h+var_12C], r13d
0x18000cbed  lea     rax, [rsp+160h+var_12C]
0x18000cbf2  mov     [rbp+60h+var_60], rax
0x18000cbf6  mov     [rsp+160h+var_120], r14
0x18000cbfb  mov     qword ptr [rsp+160h+EventDescriptor.Id], rsi
0x18000cc00  mov     [rsp+160h+var_130], ebx
0x18000cc04  mov     [rbp+60h+var_58], 4
0x18000cc0c  test    rdi, rdi
0x18000cc0f  jz      short loc_18000CC35
0x18000cc11  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000cc18  nop     dword ptr [rax+rax+00000000h]
0x18000cc20  cmp     [rdi+rax*2+2], r13w
0x18000cc26  lea     rax, [rax+1]
0x18000cc2a  jnz     short loc_18000CC20
0x18000cc2c  lea     eax, ds:2[rax*2]
0x18000cc33  jmp     short loc_18000CC41
0x18000cc35  lea     rdi, word_1800D6108
0x18000cc3c  mov     eax, 2
0x18000cc41  mov     [rbp+60h+var_68], eax
0x18000cc44  lea     rdx, [rsp+160h+var_108]; EventDescriptor
0x18000cc49  mov     [rbp+60h+var_70], rdi
0x18000cc4d  lea     rax, [rsp+160h+var_120]
0x18000cc52  mov     [rbp+60h+var_80], rax
0x18000cc56  xor     r9d, r9d; RelatedActivityId
0x18000cc59  mov     [rbp+60h+var_64], r13d
0x18000cc5d  lea     rax, [rsp+160h+EventDescriptor]
0x18000cc62  mov     [rbp+60h+var_90], rax
0x18000cc66  xor     r8d, r8d; ActivityId
0x18000cc69  lea     rax, [rsp+160h+var_130]
0x18000cc6e  mov     [rbp+60h+var_78], 8
0x18000cc76  mov     [rbp+60h+var_A0], rax
0x18000cc7a  movzx   eax, cs:word_1800FA800
0x18000cc81  mov     dword ptr [rsp+160h+var_108.Level], eax
0x18000cc85  mov     rax, [rcx+8]
0x18000cc89  mov     [rbp+60h+var_C0.Ptr], rax
0x18000cc8d  mov     [rbp+60h+var_88], 8
0x18000cc95  mov     [rbp+60h+var_98], 4
0x18000cc9d  mov     dword ptr [rsp+160h+var_108.Id], 0B000000h
0x18000cca5  mov     [rsp+160h+var_108.Keyword], 1
0x18000ccae  movzx   eax, word ptr [rax]
0x18000ccb1  mov     [rbp+60h+var_C0.Size], eax
0x18000ccb4  lea     rax, word_1800FA80A
0x18000ccbb  mov     [rbp+60h+var_B0], rax
0x18000ccbf  lea     rax, _TraceLoggingMetadata
0x18000ccc6  sub     r12d, eax
0x18000ccc9  mov     dword ptr [rbp+60h+var_C0.0Ch], 2
0x18000ccd0  mov     [rbp+60h+var_A8], 4Dh ; 'M'
0x18000ccd7  mov     [rbp+60h+var_A4], 1
0x18000ccde  mov     [rsp+160h+var_128], r12d
0x18000cce3  mov     eax, [rsp+160h+var_128]
0x18000cce7  mov     rcx, [rcx+20h]; RegHandle
0x18000cceb  lea     rax, [rbp+60h+var_C0]
0x18000ccef  mov     qword ptr [rsp+160h+InfoLevel], rax; UserData
0x18000ccf4  mov     [rsp+160h+cbMax], 7; UserDataCount
0x18000ccfc  call    cs:__imp_EventWriteTransfer
0x18000cd02  test    ebx, ebx
0x18000cd04  jnz     short loc_18000CD0E
0x18000cd06  mov     rcx, r15; struct JET_COLUMNDEF *
0x18000cd09  call    ?LogColumnDef@EseTraceLogging@@SAXAEBUJET_COLUMNDEF@@@Z; EseTraceLogging::LogColumnDef(JET_COLUMNDEF const &)
0x18000cd0e  mov     eax, ebx
0x18000cd10  mov     rcx, [rbp+60h+var_50]
0x18000cd14  xor     rcx, rsp; StackCookie
0x18000cd17  call    __security_check_cookie
0x18000cd1c  add     rsp, 128h
0x18000cd23  pop     r15
0x18000cd25  pop     r14
0x18000cd27  pop     r13
0x18000cd29  pop     r12
0x18000cd2b  pop     rdi
0x18000cd2c  pop     rsi
0x18000cd2d  pop     rbx
0x18000cd2e  pop     rbp
0x18000cd2f  retn
```
