# CHardwareManager::OnPnpHardwareChange(ulong,_DEV_BROADCAST_DEVICEINTERFACE_W *)

- ea: `0x1800458e4`
- end: `0x180045a44`
- name: `?OnPnpHardwareChange@CHardwareManager@@SAXKPEAU_DEV_BROADCAST_DEVICEINTERFACE_W@@@Z`
- size: `352`
- prototype: `void __fastcall(unsigned int, struct _DEV_BROADCAST_DEVICEINTERFACE_W *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180030780`

## callees

- `0x1800119c4`
- `0x18002a3f8`
- `0x1800458e4`
- `0x180069330`
- `0x180069cc8`
- `0x18006aea8`
- `0x18006b0b5`
- `0x18006e4c4`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x1800459d6`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180045a22`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x1800459d6`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180045a22`

## pseudocode

```c
void __fastcall CHardwareManager::OnPnpHardwareChange(int a1, struct _DEV_BROADCAST_DEVICEINTERFACE_W *a2)
{
  unsigned __int64 v4; // rsi
  struct _OVERLAPPED *v5; // rax
  struct _OVERLAPPED *v6; // rbx
  struct CHardwareManager *v7; // rax
  struct CHardwareManager *v8; // rax

  if ( a2 )
  {
    if ( a2->dbcc_size >= 0x20 && a2->dbcc_devicetype - 5 <= 1 )
    {
      v4 = ((unsigned __int64)a2->dbcc_size - 32) >> 1;
      if ( v4 - 1 <= 0xC7 && (unsigned int)(a1 - 0x8000) <= 4 )
      {
        v5 = (struct _OVERLAPPED *)operator new(0x1A0u, (const struct std::nothrow_t *)std::nothrow);
        v6 = v5;
        if ( v5 )
        {
          memset_0(v5, 0, 0x1A0u);
          memcpy_0(&v6->InternalHigh, a2->dbcc_name, 2 * v4);
          v6[12].hEvent = (HANDLE)v4;
          if ( a1 == 0x8000 )
          {
            LODWORD(v6->Internal) = 2;
          }
          else if ( (unsigned int)(a1 - 32769) <= 2 )
          {
            v6->InternalHigh = *(_QWORD *)&a2->dbcc_classguid.Data2;
            LODWORD(v6->Internal) = 5;
          }
          else
          {
            LODWORD(v6->Internal) = 3;
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl) )
          {
            v7 = CHardwareManager::Instance();
            if ( !PostQueuedCompletionStatus(*((HANDLE *)v7 + 6), 0, 0, v6) )
            {
              operator delete(v6, 0x1A0u);
              if ( (unsigned int)dword_18010F170 > 4 )
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
                  (__int64)&dword_18010F170,
                  (__int64)word_1800ECC4A);
            }
          }
          else
          {
            v8 = CHardwareManager::Instance();
            if ( !PostQueuedCompletionStatus(*((HANDLE *)v8 + 6), 0, 0, v6) )
              operator delete(v6, 0x1A0u);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800458e4  test    rdx, rdx
0x1800458e7  jz      locret_180045A43
0x1800458ed  push    rbx
0x1800458ee  push    rbp
0x1800458ef  push    rsi
0x1800458f0  push    rdi
0x1800458f1  push    r14
0x1800458f3  push    r15
0x1800458f5  sub     rsp, 28h
0x1800458f9  cmp     dword ptr [rdx], 20h ; ' '
0x1800458fc  mov     rdi, rdx
0x1800458ff  mov     ebp, ecx
0x180045901  jb      loc_180045A37
0x180045907  mov     eax, [rdx+4]
0x18004590a  sub     eax, 5
0x18004590d  cmp     eax, 1
0x180045910  ja      loc_180045A37
0x180045916  mov     esi, [rdx]
0x180045918  sub     rsi, 20h ; ' '
0x18004591c  shr     rsi, 1
0x18004591f  lea     rax, [rsi-1]
0x180045923  cmp     rax, 0C7h
0x180045929  ja      loc_180045A37
0x18004592f  lea     eax, [rcx-8000h]
0x180045935  cmp     eax, 4
0x180045938  ja      loc_180045A37
0x18004593e  mov     r15d, 1A0h
0x180045944  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004594b  mov     ecx, r15d; unsigned __int64
0x18004594e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180045953  mov     rbx, rax
0x180045956  test    rax, rax
0x180045959  jz      loc_180045A37
0x18004595f  mov     r8d, r15d; Size
0x180045962  xor     edx, edx; Val
0x180045964  mov     rcx, rax; void *
0x180045967  call    memset_0
0x18004596c  lea     r8, [rsi+rsi]; Size
0x180045970  lea     rdx, [rdi+1Ch]; Src
0x180045974  lea     rcx, [rbx+8]; void *
0x180045978  call    memcpy_0
0x18004597d  mov     [rbx+198h], rsi
0x180045984  cmp     ebp, 8000h
0x18004598a  jnz     short loc_180045994
0x18004598c  mov     dword ptr [rbx], 2
0x180045992  jmp     short loc_1800459B5
0x180045994  lea     eax, [rbp-8001h]
0x18004599a  cmp     eax, 2
0x18004599d  jbe     short loc_1800459A7
0x18004599f  mov     dword ptr [rbx], 3
0x1800459a5  jmp     short loc_1800459B5
0x1800459a7  mov     rax, [rdi+10h]
0x1800459ab  mov     [rbx+8], rax
0x1800459af  mov     dword ptr [rbx], 5
0x1800459b5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EssFprPeripherals@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals> `wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl(void)'::`2'::impl
0x1800459bc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(void)
0x1800459c1  test    al, al
0x1800459c3  jz      short loc_180045A11
0x1800459c5  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800459ca  mov     r9, rbx; lpOverlapped
0x1800459cd  xor     r8d, r8d; dwCompletionKey
0x1800459d0  xor     edx, edx; dwNumberOfBytesTransferred
0x1800459d2  mov     rcx, [rax+30h]; CompletionPort
0x1800459d6  call    cs:__imp_PostQueuedCompletionStatus
0x1800459dc  test    eax, eax
0x1800459de  jnz     short loc_180045A37
0x1800459e0  mov     rdx, r15; unsigned __int64
0x1800459e3  mov     rcx, rbx; void *
0x1800459e6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800459eb  mov     eax, cs:dword_18010F170
0x1800459f1  cmp     eax, 4
0x1800459f4  jbe     short loc_180045A37
0x1800459f6  xor     r9d, r9d
0x1800459f9  lea     rdx, word_1800ECC4A
0x180045a00  xor     r8d, r8d
0x180045a03  lea     rcx, dword_18010F170
0x180045a0a  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180045a0f  jmp     short loc_180045A37
0x180045a11  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180045a16  mov     r9, rbx; lpOverlapped
0x180045a19  xor     r8d, r8d; dwCompletionKey
0x180045a1c  xor     edx, edx; dwNumberOfBytesTransferred
0x180045a1e  mov     rcx, [rax+30h]; CompletionPort
0x180045a22  call    cs:__imp_PostQueuedCompletionStatus
0x180045a28  test    eax, eax
0x180045a2a  jnz     short loc_180045A37
0x180045a2c  mov     rdx, r15; unsigned __int64
0x180045a2f  mov     rcx, rbx; void *
0x180045a32  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180045a37  add     rsp, 28h
0x180045a3b  pop     r15
0x180045a3d  pop     r14
0x180045a3f  pop     rdi
0x180045a40  pop     rsi
0x180045a41  pop     rbp
0x180045a42  pop     rbx
0x180045a43  retn
```
