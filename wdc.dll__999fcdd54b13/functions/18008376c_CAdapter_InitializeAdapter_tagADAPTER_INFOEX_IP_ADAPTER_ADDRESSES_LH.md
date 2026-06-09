# CAdapter::InitializeAdapter(tagADAPTER_INFOEX * *,_IP_ADAPTER_ADDRESSES_LH *)

- ea: `0x18008376c`
- end: `0x1800839c0`
- name: `?InitializeAdapter@CAdapter@@AEAAJPEAPEAUtagADAPTER_INFOEX@@PEAU_IP_ADAPTER_ADDRESSES_LH@@@Z`
- size: `596`
- prototype: `__int64 __fastcall(CAdapter *__hidden this, struct tagADAPTER_INFOEX **, struct _IP_ADAPTER_ADDRESSES_LH *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001ac14`

## callees

- `0x18000b7d0`
- `0x18001a860`
- `0x18001cb20`
- `0x18001e524`
- `0x18003b0ac`
- `0x18008376c`
- `0x180084e1c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180083892`
- `ntdll!RtlInitUnicodeString` at `0x180083892`
- `KERNEL32!GetProcessHeap` at `0x1800837ab`
- `KERNEL32!GetProcessHeap` at `0x1800837ab`
- `KERNEL32!HeapAlloc` at `0x1800837bd`
- `KERNEL32!HeapAlloc` at `0x1800837bd`
- `ole32!CoTaskMemFree` at `0x180083881`
- `ole32!CoTaskMemFree` at `0x180083881`
- `ole32!StringFromCLSID` at `0x180083847`
- `ole32!StringFromCLSID` at `0x180083847`
- `IPHLPAPI!GetIfEntry2` at `0x1800837ee`
- `IPHLPAPI!GetIfEntry2` at `0x1800837ee`

## pseudocode

```c
__int64 __fastcall CAdapter::InitializeAdapter(
        OLECHAR *this,
        struct _MIB_IF_ROW2 **a2,
        struct _IP_ADAPTER_ADDRESSES_LH *a3)
{
  struct _MIB_IF_ROW2 *v5; // rbx
  unsigned int v6; // esi
  HANDLE ProcessHeap; // rax
  struct tagADAPTER_INFOEX *v8; // rax
  IFTYPE Type; // eax
  const IID *p_InterfaceGuid; // rbx
  __int64 v11; // rcx
  CAdapter *v12; // rcx
  unsigned int v13; // r9d
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-98h] BYREF
  int v16; // [rsp+30h] [rbp-88h] BYREF
  _BYTE v17[16]; // [rsp+34h] [rbp-84h] BYREF
  unsigned int v18; // [rsp+44h] [rbp-74h]
  LPOLESTR lpsz; // [rsp+C0h] [rbp+8h] BYREF

  lpsz = this;
  if ( !a2 || !a3 )
    return 2147942487LL;
  v5 = *a2;
  v6 = -2147024882;
  if ( *a2
    || (ProcessHeap = GetProcessHeap(),
        v8 = (struct tagADAPTER_INFOEX *)HeapAlloc(ProcessHeap, 8u, 0x17F8u),
        *a2 = (struct _MIB_IF_ROW2 *)v8,
        (v5 = (struct _MIB_IF_ROW2 *)v8) != 0) )
  {
    memset_0(v5, 0, sizeof(struct _MIB_IF_ROW2));
    v5->InterfaceIndex = a3->IfIndex;
    if ( !GetIfEntry2(v5) )
    {
      Type = v5->Type;
      if ( Type == 23 || Type == 28 )
      {
        p_InterfaceGuid = &v5->InterfaceGuid;
        LOBYTE((*a2)[3].Alias[230]) = 1;
      }
      else
      {
        memset_0(v17, 0, 0x64u);
        lpsz = 0;
        p_InterfaceGuid = &v5->InterfaceGuid;
        DestinationString = 0;
        if ( StringFromCLSID(p_InterfaceGuid, &lpsz) >= 0 )
        {
          StringCchPrintfW(
            &(*a2)[4].Alias[88],
            0x104u,
            L"\\Device\\%s",
            lpsz,
            *(_QWORD *)&DestinationString.Length,
            DestinationString.Buffer);
          CoTaskMemFree(lpsz);
          RtlInitUnicodeString(&DestinationString, &(*a2)[4].Alias[88]);
          v16 = 104;
          if ( (unsigned int)NdisQueryStatistics(&DestinationString, &v16) )
            v11 = 100LL * v18;
          else
            v11 = 0;
          *(_QWORD *)&(*a2)[3].Alias[226] = v11;
          LOBYTE((*a2)[3].Alias[230]) = 0;
        }
      }
      memcpy_0(&(*a2)[1], *a2, sizeof(struct _MIB_IF_ROW2));
      memcpy_0(&(*a2)[2], *a2, sizeof(struct _MIB_IF_ROW2));
      memset_0(&(*a2)[3], -1, 0xF0u);
      memset_0(&(*a2)[3].Alias[106], -1, 0xF0u);
      StringCchCopyW(&(*a2)[3].Alias[231], 0x100u, (*a2)->Description);
      *(IID *)&(*a2)[4].Alias[68] = *p_InterfaceGuid;
      HIBYTE((*a2)[3].Alias[230]) = 1;
      if ( (int)CAdapter::GetConnectionName(v12, (struct _GUID *)&(*a2)[4].Alias[68], &(*a2)[3].Description[230], v13) < 0 )
        StringCchCopyW(&(*a2)[3].Description[230], 0x100u, &(*a2)[3].Alias[231]);
      return 0;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18008376c  mov     [rsp+arg_8], rbx
0x180083771  mov     [rsp+arg_10], rbp
0x180083776  mov     [rsp+lpsz], rcx
0x18008377b  push    rsi
0x18008377c  push    rdi
0x18008377d  push    r14
0x18008377f  sub     rsp, 0A0h
0x180083786  mov     rbp, r8
0x180083789  mov     rdi, rdx
0x18008378c  test    rdx, rdx
0x18008378f  jz      loc_1800839A3
0x180083795  test    r8, r8
0x180083798  jz      loc_1800839A3
0x18008379e  mov     rbx, [rdx]
0x1800837a1  mov     esi, 8007000Eh
0x1800837a6  test    rbx, rbx
0x1800837a9  jnz     short loc_1800837D2
0x1800837ab  call    cs:__imp_GetProcessHeap
0x1800837b1  lea     edx, [rbx+8]; dwFlags
0x1800837b4  mov     r8d, 17F8h; dwBytes
0x1800837ba  mov     rcx, rax; hHeap
0x1800837bd  call    cs:__imp_HeapAlloc
0x1800837c3  mov     [rdi], rax
0x1800837c6  mov     rbx, rax
0x1800837c9  test    rax, rax
0x1800837cc  jz      loc_18008399F
0x1800837d2  mov     r14d, 548h
0x1800837d8  xor     edx, edx; Val
0x1800837da  mov     r8d, r14d; Size
0x1800837dd  mov     rcx, rbx; void *
0x1800837e0  call    memset_0
0x1800837e5  mov     eax, [rbp+4]
0x1800837e8  mov     rcx, rbx; Row
0x1800837eb  mov     [rbx+8], eax
0x1800837ee  call    cs:__imp_GetIfEntry2
0x1800837f4  test    eax, eax
0x1800837f6  jnz     loc_18008399F
0x1800837fc  mov     eax, [rbx+468h]
0x180083802  cmp     eax, 17h
0x180083805  jz      loc_1800838D5
0x18008380b  cmp     eax, 1Ch
0x18008380e  jz      loc_1800838D5
0x180083814  xor     edx, edx; Val
0x180083816  lea     rcx, [rsp+0B8h+var_84]; void *
0x18008381b  lea     r8d, [rdx+64h]; Size
0x18008381f  call    memset_0
0x180083824  xorps   xmm0, xmm0
0x180083827  mov     [rsp+0B8h+lpsz], 0
0x180083833  add     rbx, 0Ch
0x180083837  lea     rdx, [rsp+0B8h+lpsz]; lplpsz
0x18008383f  mov     rcx, rbx; rclsid
0x180083842  movups  xmmword ptr [rsp+0B8h+DestinationString.Length], xmm0
0x180083847  call    cs:__imp_StringFromCLSID
0x18008384d  test    eax, eax
0x18008384f  js      loc_1800838E3
0x180083855  mov     rcx, [rdi]
0x180083858  lea     r8, aDeviceS; "\\Device\\%s"
0x18008385f  mov     r9, [rsp+0B8h+lpsz]
0x180083867  mov     esi, 15ECh
0x18008386c  add     rcx, rsi; unsigned __int16 *
0x18008386f  mov     edx, 104h; unsigned __int64
0x180083874  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180083879  mov     rcx, [rsp+0B8h+lpsz]; pv
0x180083881  call    cs:__imp_CoTaskMemFree
0x180083887  mov     rdx, [rdi]
0x18008388a  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x18008388f  add     rdx, rsi; SourceString
0x180083892  call    cs:__imp_RtlInitUnicodeString
0x180083898  lea     rdx, [rsp+0B8h+var_88]
0x18008389d  mov     [rsp+0B8h+var_88], 68h ; 'h'
0x1800838a5  lea     rcx, [rsp+0B8h+DestinationString]
0x1800838aa  call    NdisQueryStatistics
0x1800838af  mov     rdx, [rdi]
0x1800838b2  test    eax, eax
0x1800838b4  jz      short loc_1800838C0
0x1800838b6  mov     eax, [rsp+0B8h+var_74]
0x1800838ba  imul    rcx, rax, 64h ; 'd'
0x1800838be  jmp     short loc_1800838C2
0x1800838c0  xor     ecx, ecx
0x1800838c2  mov     [rdx+11B8h], rcx
0x1800838c9  mov     rax, [rdi]
0x1800838cc  mov     byte ptr [rax+11C0h], 0
0x1800838d3  jmp     short loc_1800838E3
0x1800838d5  mov     rax, [rdi]
0x1800838d8  add     rbx, 0Ch
0x1800838dc  mov     byte ptr [rax+11C0h], 1
0x1800838e3  mov     rdx, [rdi]; Src
0x1800838e6  mov     r8, r14; Size
0x1800838e9  lea     rcx, [rdx+548h]; void *
0x1800838f0  call    memcpy_0
0x1800838f5  mov     rdx, [rdi]; Src
0x1800838f8  mov     r8, r14; Size
0x1800838fb  lea     rcx, [rdx+0A90h]; void *
0x180083902  call    memcpy_0
0x180083907  mov     rcx, [rdi]
0x18008390a  mov     ebp, 0F0h
0x18008390f  or      esi, 0FFFFFFFFh
0x180083912  add     rcx, 0FD8h; void *
0x180083919  mov     r8d, ebp; Size
0x18008391c  mov     edx, esi; Val
0x18008391e  call    memset_0
0x180083923  mov     rcx, [rdi]
0x180083926  mov     r8d, ebp; Size
0x180083929  add     rcx, 10C8h; void *
0x180083930  mov     edx, esi; Val
0x180083932  call    memset_0
0x180083937  mov     rcx, [rdi]
0x18008393a  lea     esi, [rbp+10h]
0x18008393d  mov     edx, esi; unsigned __int64
0x18008393f  lea     r8, [rcx+21Eh]; unsigned __int16 *
0x180083946  add     rcx, 11C2h; unsigned __int16 *
0x18008394d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180083952  mov     r11, [rdi]
0x180083955  movups  xmm0, xmmword ptr [rbx]
0x180083958  movdqu  xmmword ptr [r11+15C4h], xmm0
0x180083961  mov     rax, [rdi]
0x180083964  mov     byte ptr [rax+11C1h], 1
0x18008396b  mov     rdx, [rdi]
0x18008396e  lea     r8, [rdx+13C2h]; unsigned __int16 *
0x180083975  add     rdx, 15C4h; struct _GUID *
0x18008397c  call    ?GetConnectionName@CAdapter@@AEAAJPEAU_GUID@@PEAGK@Z; CAdapter::GetConnectionName(_GUID *,ushort *,ulong)
0x180083981  test    eax, eax
0x180083983  jns     short loc_18008399D
0x180083985  mov     rcx, [rdi]
0x180083988  mov     edx, esi; unsigned __int64
0x18008398a  lea     r8, [rcx+11C2h]; unsigned __int16 *
0x180083991  add     rcx, 13C2h; unsigned __int16 *
0x180083998  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008399d  xor     esi, esi
0x18008399f  mov     eax, esi
0x1800839a1  jmp     short loc_1800839A8
0x1800839a3  mov     eax, 80070057h
0x1800839a8  lea     r11, [rsp+0B8h+var_18]
0x1800839b0  mov     rbx, [r11+28h]
0x1800839b4  mov     rbp, [r11+30h]
0x1800839b8  mov     rsp, r11
0x1800839bb  pop     r14
0x1800839bd  pop     rdi
0x1800839be  pop     rsi
0x1800839bf  retn
```
