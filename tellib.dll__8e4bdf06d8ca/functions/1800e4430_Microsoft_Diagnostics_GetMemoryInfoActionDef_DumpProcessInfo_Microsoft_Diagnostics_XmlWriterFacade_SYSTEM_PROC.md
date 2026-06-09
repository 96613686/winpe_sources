# Microsoft::Diagnostics::GetMemoryInfoActionDef::DumpProcessInfo(Microsoft::Diagnostics::XmlWriterFacade &,_SYSTEM_PROCESS_INFORMATION const &,ulong,_EDP_ENFORCEMENT_LEVEL,Microsoft::Diagnostics::EscalationWorkItemState &)

- ea: `0x1800e4430`
- end: `0x1800e54de`
- name: `?DumpProcessInfo@GetMemoryInfoActionDef@Diagnostics@Microsoft@@AEBAXAEAVXmlWriterFacade@23@AEBU_SYSTEM_PROCESS_INFORMATION@@KW4_EDP_ENFORCEMENT_LEVEL@@AEAVEscalationWorkItemState@23@@Z`
- size: `4270`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1802f7410`

## callees

- `0x18001d160`
- `0x180020fbc`
- `0x180024ee0`
- `0x180053a84`
- `0x1800558c0`
- `0x180081c84`
- `0x1800b2d34`
- `0x1800daaac`
- `0x1800e2fd8`
- `0x1800e4430`
- `0x1800e54e4`
- `0x1800f76bc`
- `0x18012de40`
- `0x18012de64`
- `0x180159874`
- `0x1801fb620`
- `0x1802e4fc0`
- `0x1802e50d0`
- `0x1802e5448`
- `0x1802e5560`
- `0x1802e5670`
- `0x1802f52a8`
- `0x1802f5650`
- `0x1802f5778`
- `0x1802f5798`
- `0x1802f589c`
- `0x1802f6fa4`
- `0x1802f7a24`

## import_xrefs

- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForProcess` at `0x1800e51d9`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForProcess` at `0x1800e51d9`

## string_xrefs

- `0x1800e495f`: `UniqueProcessId`
- `0x1800e4716`: `NumberOfThreads`
- `0x1800e47cd`: `NumberOfThreadsHighWatermark`
- `0x1800e4857`: `CreateTime`
- `0x1800e4e56`: `WriteOperationCount`
- `0x1800e4ed4`: `ReadTransferCount`
- `0x1800e4f0c`: `WriteTransferCount`
- `0x1800e4e13`: `ReadOperationCount`
- `0x1800e49ac`: `InheritedFromUniqueProcessId`
- `0x1800e4637`: `serviceinfo`
- `0x1800e468c`: `ServiceName`
- `0x1800e5452`: `ServiceName`
- `0x1800e4f88`: `DiskCounters.BytesRead`
- `0x1800e504d`: `DiskCounters.ReadOperationCount`
- `0x1800e549f`: `ServiceQueryWmiError`
- `0x1800e53f9`: `ServiceQueryScmError`
- `0x1800e508f`: `DiskCounters.WriteOperationCount`
- `0x1800e515b`: `threads`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall Microsoft::Diagnostics::GetMemoryInfoActionDef::DumpProcessInfo(
        _QWORD *a1,
        struct Microsoft::Diagnostics::XmlWriterFacade *a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        __int64 a6)
{
  __int64 v6; // r14
  unsigned int *v10; // r12
  __int64 v11; // r15
  __int64 v12; // r14
  _QWORD *v13; // r9
  _QWORD *v14; // rcx
  __int64 v15; // r13
  const wchar_t *v16; // rcx
  int v17; // eax
  __int64 v18; // r15
  __int64 v19; // rbx
  Microsoft::Diagnostics::GetMemoryInfoActionDef *v20; // rcx
  unsigned int j; // ebx
  unsigned int v22; // ebx
  const wchar_t *k; // rax
  __int64 v24; // rax
  __int64 v25; // rdx
  const wchar_t *i; // rbx
  const wchar_t *v27; // [rsp+30h] [rbp-99h] BYREF
  __int64 v28; // [rsp+38h] [rbp-91h]
  const wchar_t *v29; // [rsp+40h] [rbp-89h] BYREF
  __int64 v30; // [rsp+48h] [rbp-81h]
  _DWORD v31[4]; // [rsp+50h] [rbp-79h] BYREF
  __int64 v32[2]; // [rsp+60h] [rbp-69h] BYREF
  const wchar_t *v33; // [rsp+70h] [rbp-59h] BYREF
  __int64 v34; // [rsp+78h] [rbp-51h]
  __int128 v35; // [rsp+80h] [rbp-49h] BYREF
  __int64 v36; // [rsp+90h] [rbp-39h] BYREF
  __int64 v37; // [rsp+98h] [rbp-31h]
  _BYTE v38[16]; // [rsp+A8h] [rbp-21h] BYREF
  _DWORD v39[4]; // [rsp+B8h] [rbp-11h] BYREF
  __int64 v40; // [rsp+C8h] [rbp-1h]
  unsigned __int64 v41; // [rsp+D0h] [rbp+7h]

  v6 = a4;
  v32[0] = a6;
  Microsoft::Diagnostics::GetMemoryInfoActionDef::GetPathlessProcessName(v39, a3);
  if ( !a1[18] || (_DWORD)v6 && *(_QWORD *)(a3 + 80) == v6 )
  {
    v10 = (unsigned int *)(a3 + 4);
    v11 = *(unsigned int *)(a3 + 4);
    v12 = -1;
    if ( !a1[22] )
      goto LABEL_10;
    v13 = a1 + 20;
    if ( a1[23] > 7u )
      v13 = (_QWORD *)*v13;
    v14 = v39;
    if ( v41 > 7 )
      LODWORD(v14) = v39[0];
    if ( std::_Traits_find<std::char_traits<wchar_t>>((_DWORD)v14, v40, 0, (_DWORD)v13, a1[22]) != -1 )
    {
LABEL_10:
      v15 = a3 + 136 * v11 + 256;
      v33 = L"process";
      v34 = 7;
      Microsoft::Diagnostics::XmlWriterFacade::CreateElement(a2, v38, &v33);
      v33 = L"identifyinginfo";
      v34 = 15;
      Microsoft::Diagnostics::XmlWriterFacade::CreateElement(a2, &v35, &v33);
      v33 = L"ImageName";
      v34 = 9;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<std::wstring>(a2, &v29, &v33, v39);
      if ( *(_DWORD *)(v15 + 56) )
      {
        v16 = (const wchar_t *)(v15 + *(unsigned int *)(v15 + 56));
        v29 = v16;
        do
          ++v12;
        while ( v16[v12] );
        v30 = v12;
        v33 = L"PackageFullName";
        v34 = 15;
        v27 = L"info";
        v28 = 4;
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<std::wstring_view>(a2, &v27, &v33, &v29);
      }
      Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)&v35);
      v27 = L"svchost.exe";
      v28 = 11;
      v35 = *(_OWORD *)std::wstring::operator std::wstring_view(v39, &v29);
      if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v35, &v27) )
      {
        v27 = L"serviceinfo";
        v28 = 11;
        Microsoft::Diagnostics::XmlWriterFacade::CreateElement(a2, &v35, &v27);
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>(&v36);
        v17 = Microsoft::Diagnostics::Utils::Os::EnumerateServicesInProcess(*(unsigned int *)(a3 + 80), &v36);
        v31[0] = v17;
        if ( v17 < 0 )
        {
          if ( v17 == -2147221164 )
          {
            if ( !a1[25] )
            {
              v33 = (const wchar_t *)operator new(0x40u);
              v24 = std::unordered_multimap<unsigned long,std::wstring>::unordered_multimap<unsigned long,std::wstring>(v33);
              v33 = 0;
              v25 = a1[25];
              a1[25] = v24;
              if ( v25 )
                std::default_delete<std::unordered_multimap<unsigned long,std::wstring>>::operator()();
              std::unique_ptr<std::unordered_multimap<unsigned long,std::wstring>>::~unique_ptr<std::unordered_multimap<unsigned long,std::wstring>>(&v33);
              v27 = L".*";
              v28 = 2;
              v31[0] = Microsoft::Diagnostics::Utils::Os::GetServiceProcessIdsRegex(&v27, 1u, a1[25], v32[0]);
              if ( v31[0] < 0 )
              {
                v27 = L"ServiceQueryScmError";
                v28 = 20;
                v29 = L"info";
                v30 = 4;
                Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<long>(a2, &v29, &v27, v31);
              }
            }
            v31[0] = *(_DWORD *)(a3 + 80);
            std::_Hash<std::_Umap_traits<unsigned long,Microsoft::Diagnostics::AppIdMetadata::SessionInfo,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,Microsoft::Diagnostics::AppIdMetadata::SessionInfo>>,1>>::equal_range(
              a1[25],
              &v27,
              v31);
            for ( i = v27; i != (const wchar_t *)v28; i = *(const wchar_t **)i )
            {
              v29 = L"ServiceName";
              v30 = 11;
              v32[0] = (__int64)L"info";
              v32[1] = 4;
              Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<std::wstring>(a2, v32, &v29, i + 12);
            }
          }
          else
          {
            v27 = L"ServiceQueryWmiError";
            v28 = 20;
            v29 = L"info";
            v30 = 4;
            Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<long>(a2, &v29, &v27, v31);
          }
        }
        else
        {
          v18 = v37;
          v19 = v36;
          if ( v36 != v37 )
          {
            do
            {
              v27 = L"ServiceName";
              v28 = 11;
              v29 = L"info";
              v30 = 4;
              Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<std::wstring>(a2, &v29, &v27, v19);
              v19 += 32;
            }
            while ( v19 != v18 );
            v10 = (unsigned int *)(a3 + 4);
          }
        }
        std::vector<std::wstring>::_Tidy(&v36);
        Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)&v35);
      }
      v27 = L"performanceinfo";
      v28 = 15;
      Microsoft::Diagnostics::XmlWriterFacade::CreateElement(a2, &v35, &v27);
      v27 = L"NumberOfThreads";
      v28 = 15;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
        (_DWORD)a2,
        (unsigned int)&v29,
        (unsigned int)&v27,
        (_DWORD)v10,
        0);
      v27 = L"WorkingSetPrivateSize";
      v28 = 21;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(a2, &v29, &v27, a3 + 8);
      v27 = L"HardFaultCount";
      v28 = 14;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
        (_DWORD)a2,
        (unsigned int)&v29,
        (unsigned int)&v27,
        a3 + 16,
        0);
      v27 = L"NumberOfThreadsHighWatermark";
      v28 = 28;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
        (_DWORD)a2,
        (unsigned int)&v29,
        (unsigned int)&v27,
        a3 + 20,
        0);
      v27 = L"CycleTime";
      v28 = 9;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
        (_DWORD)a2,
        (unsigned int)&v29,
        (unsigned int)&v27,
        a3 + 24,
        0);
      v27 = L"CreateTime";
      v28 = 10;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(a2, &v29, &v27, a3 + 32);
      v27 = L"UserTime";
      v28 = 8;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(a2, &v29, &v27, a3 + 40);
      v27 = L"KernelTime";
      v28 = 10;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(a2, &v29, &v27, a3 + 48);
      v27 = L"BasePriority";
      v28 = 12;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<long>(a2, &v29, &v27, a3 + 72);
      v32[0] = *(_QWORD *)(a3 + 80);
      v27 = L"UniqueProcessId";
      v28 = 15;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
        (_DWORD)a2,
        (unsigned int)&v29,
        (unsigned int)&v27,
        (unsigned int)v32,
        0);
      v32[0] = *(_QWORD *)(a3 + 88);
      v27 = L"InheritedFromUniqueProcessId";
      v28 = 28;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
        (_DWORD)a2,
        (unsigned int)&v29,
        (unsigned int)&v27,
        (unsigned int)v32,
        0);
      v27 = L"HandleCount";
      v28 = 11;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
        (_DWORD)a2,
        (unsigned int)&v29,
        (unsigned int)&v27,
        a3 + 96,
        0);
      v27 = (const wchar_t *)L"SessionId";
      v28 = 9;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
        (_DWORD)a2,
        (unsigned int)&v29,
        (unsigned int)&v27,
        a3 + 100,
        0);
      v32[0] = *(_QWORD *)(a3 + 104);
      v27 = L"UniqueProcessKey";
      v28 = 16;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
        (_DWORD)a2,
        (unsigned int)&v29,
        (unsigned int)&v27,
        (unsigned int)v32,
        0);
      v32[0] = *(_QWORD *)(a3 + 112);
      v27 = L"PeakVirtualSize";
      v28 = 15;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
        (_DWORD)a2,
        (unsigned int)&v29,
        (unsigned int)&v27,
        (unsigned int)v32,
        0);
      v32[0] = *(_QWORD *)(a3 + 120);
      v27 = L"VirtualSize";
      v28 = 11;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
        (_DWORD)a2,
        (unsigned int)&v29,
        (unsigned int)&v27,
        (unsigned int)v32,
        0);
      v27 = L"PageFaultCount";
      v28 = 14;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
        (_DWORD)a2,
        (unsigned int)&v29,
        (unsigned int)&v27,
        a3 + 128,
        0);
      v32[0] = *(_QWORD *)(a3 + 136);
      v27 = L"PeakWorkingSetSize";
      v28 = 18;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
        (_DWORD)a2,
        (unsigned int)&v29,
        (unsigned int)&v27,
        (unsigned int)v32,
        0);
      v32[0] = *(_QWORD *)(a3 + 144);
      v27 = L"WorkingSetSize";
      v28 = 14;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
        (_DWORD)a2,
        (unsigned int)&v29,
        (unsigned int)&v27,
        (unsigned int)v32,
        0);
      v32[0] = *(_QWORD *)(a3 + 152);
      v27 = L"QuotaPeakPagedPoolUsage";
      v28 = 23;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
        (_DWORD)a2,
        (unsigned int)&v29,
        (unsigned int)&v27,
        (unsigned int)v32,
        0);
      v32[0] = *(_QWORD *)(a3 + 160);
      v27 = L"QuotaPagedPoolUsage";
      v28 = 19;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
        (_DWORD)a2,
        (unsigned int)&v29,
        (unsigned int)&v27,
        (unsigned int)v32,
        0);
      v32[0] = *(_QWORD *)(a3 + 168);
      v27 = L"QuotaPeakNonPagedPoolUsage";
      v28 = 26;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
        (_DWORD)a2,
        (unsigned int)&v29,
        (unsigned int)&v27,
        (unsigned int)v32,
        0);
      v32[0] = *(_QWORD *)(a3 + 176);
      v27 = L"QuotaNonPagedPoolUsage";
      v28 = 22;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
        (_DWORD)a2,
        (unsigned int)&v29,
        (unsigned int)&v27,
        (unsigned int)v32,
        0);
      v32[0] = *(_QWORD *)(a3 + 184);
      v27 = L"PagefileUsage";
      v28 = 13;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
        (_DWORD)a2,
        (unsigned int)&v29,
        (unsigned int)&v27,
        (unsigned int)v32,
        0);
      v32[0] = *(_QWORD *)(a3 + 192);
      v27 = L"PeakPagefileUsage";
      v28 = 17;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
        (_DWORD)a2,
        (unsigned int)&v29,
        (unsigned int)&v27,
        (unsigned int)v32,
        0);
      v32[0] = *(_QWORD *)(a3 + 200);
      v27 = L"PrivatePageCount";
      v28 = 16;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
        (_DWORD)a2,
        (unsigned int)&v29,
        (unsigned int)&v27,
        (unsigned int)v32,
        0);
      v27 = L"ReadOperationCount";
      v28 = 18;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(a2, &v29, &v27, a3 + 208);
      v27 = L"WriteOperationCount";
      v28 = 19;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(a2, &v29, &v27, a3 + 216);
      v27 = L"OtherOperationCount";
      v28 = 19;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(a2, &v29, &v27, a3 + 224);
      v27 = L"ReadTransferCount";
      v28 = 17;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(a2, &v29, &v27, a3 + 232);
      v27 = L"WriteTransferCount";
      v28 = 18;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(a2, &v29, &v27, a3 + 240);
      v27 = L"OtherTransferCount";
      v28 = 18;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(a2, &v29, &v27, a3 + 248);
      v32[0] = *(_QWORD *)v15;
      v27 = L"DiskCounters.BytesRead";
      v28 = 22;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
        (_DWORD)a2,
        (unsigned int)&v29,
        (unsigned int)&v27,
        (unsigned int)v32,
        0);
      v32[0] = *(_QWORD *)(v15 + 8);
      v27 = L"DiskCounters.BytesWritten";
      v28 = 25;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
        (_DWORD)a2,
        (unsigned int)&v29,
        (unsigned int)&v27,
        (unsigned int)v32,
        0);
      v32[0] = *(_QWORD *)(v15 + 32);
      v27 = L"DiskCounters.FlushOperationCount";
      v28 = 32;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
        (_DWORD)a2,
        (unsigned int)&v29,
        (unsigned int)&v27,
        (unsigned int)v32,
        0);
      v32[0] = *(_QWORD *)(v15 + 16);
      v27 = L"DiskCounters.ReadOperationCount";
      v28 = 31;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
        (_DWORD)a2,
        (unsigned int)&v29,
        (unsigned int)&v27,
        (unsigned int)v32,
        0);
      v32[0] = *(_QWORD *)(v15 + 24);
      v27 = L"DiskCounters.WriteOperationCount";
      v28 = 32;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
        (_DWORD)a2,
        (unsigned int)&v29,
        (unsigned int)&v27,
        (unsigned int)v32,
        0);
      v31[0] = *(_DWORD *)(v15 + 48) & 1;
      v27 = L"HasStrongId";
      v28 = 11;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
        (_DWORD)a2,
        (unsigned int)&v29,
        (unsigned int)&v27,
        (unsigned int)v31,
        0);
      v31[0] = *(_DWORD *)(v15 + 48) >> 6;
      v27 = L"Spare";
      v28 = 5;
      v29 = L"info";
      v30 = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
        (_DWORD)a2,
        (unsigned int)&v29,
        (unsigned int)&v27,
        (unsigned int)v31,
        0);
      Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)&v35);
      v27 = L"threads";
      v28 = 7;
      Microsoft::Diagnostics::XmlWriterFacade::CreateElement(a2, &v35, &v27);
      for ( j = 0; j < *v10; ++j )
        Microsoft::Diagnostics::GetMemoryInfoActionDef::DumpThreadInfo(
          v20,
          a2,
          (const struct _SYSTEM_EXTENDED_THREAD_INFORMATION *)(a3 + 256 + 136LL * j));
      Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)&v35);
      if ( (unsigned __int8)IsEdpGetContextForProcessPresent() && a5 )
      {
        v33 = 0;
        if ( (int)EdpGetContextForProcess(*(unsigned int *)(a3 + 80), &v33) >= 0 )
        {
          v27 = L"edpcontext";
          v28 = 10;
          Microsoft::Diagnostics::XmlWriterFacade::CreateElement(a2, v32, &v27);
          v27 = L"allowedenterpriseids";
          v28 = 20;
          Microsoft::Diagnostics::XmlWriterFacade::CreateElement(a2, &v35, &v27);
          v22 = 0;
          for ( k = v33; v22 < *((_DWORD *)k + 1); ++v22 )
          {
            if ( *(_QWORD *)&k[4 * v22 + 8] )
            {
              v27 = L"ID";
              v28 = 2;
              v29 = L"info";
              v30 = 4;
              Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a2, &v29, &v27);
              k = v33;
            }
          }
          Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)&v35);
          v27 = L"flags";
          v28 = 5;
          Microsoft::Diagnostics::XmlWriterFacade::CreateElement(a2, &v35, &v27);
          v31[0] = *(_DWORD *)v33;
          v27 = L"Flags";
          v28 = 5;
          v29 = L"info";
          v30 = 4;
          Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
            (_DWORD)a2,
            (unsigned int)&v29,
            (unsigned int)&v27,
            (unsigned int)v31,
            1);
          Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)&v35);
          Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)v32);
        }
        wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(&v33);
      }
      Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)v38);
    }
  }
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v39);
}

```

## disassembly

```asm
0x1800e4430  mov     [rsp-8+arg_18], rbx
0x1800e4435  push    rbp
0x1800e4436  push    rsi
0x1800e4437  push    rdi
0x1800e4438  push    r12
0x1800e443a  push    r13
0x1800e443c  push    r14
0x1800e443e  push    r15
0x1800e4440  lea     rbp, [rsp-17h]
0x1800e4445  sub     rsp, 0E0h
0x1800e444c  mov     rax, cs:__security_cookie
0x1800e4453  xor     rax, rsp
0x1800e4456  mov     [rbp+47h+var_38], rax
0x1800e445a  mov     r14d, r9d
0x1800e445d  mov     rsi, r8
0x1800e4460  mov     rdi, rdx
0x1800e4463  mov     rbx, rcx
0x1800e4466  mov     rax, [rbp+47h+arg_28]
0x1800e446a  mov     [rbp+47h+var_B0], rax
0x1800e446e  xor     r13d, r13d
0x1800e4471  mov     rdx, r8
0x1800e4474  lea     rcx, [rbp+47h+var_58]
0x1800e4478  call    ?GetPathlessProcessName@GetMemoryInfoActionDef@Diagnostics@Microsoft@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_SYSTEM_PROCESS_INFORMATION@@@Z; Microsoft::Diagnostics::GetMemoryInfoActionDef::GetPathlessProcessName(_SYSTEM_PROCESS_INFORMATION const &)
0x1800e447d  nop
0x1800e447e  cmp     [rbx+90h], r13
0x1800e4485  jz      short loc_1800E449A
0x1800e4487  test    r14d, r14d
0x1800e448a  jz      loc_1800E533E
0x1800e4490  cmp     [rsi+50h], r14
0x1800e4494  jnz     loc_1800E533E
0x1800e449a  lea     r12, [rsi+4]
0x1800e449e  mov     r15d, [r12]
0x1800e44a2  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800e44a6  cmp     [rbx+0B0h], r13
0x1800e44ad  jz      short loc_1800E44EC
0x1800e44af  lea     r9, [rbx+0A0h]
0x1800e44b6  mov     rax, [r9+10h]
0x1800e44ba  cmp     qword ptr [r9+18h], 7
0x1800e44bf  jbe     short loc_1800E44C4
0x1800e44c1  mov     r9, [r9]
0x1800e44c4  lea     rcx, [rbp+47h+var_58]
0x1800e44c8  cmp     [rbp+47h+var_40], 7
0x1800e44cd  cmova   rcx, qword ptr [rbp+47h+var_58]
0x1800e44d2  mov     [rsp+110h+var_F0], rax
0x1800e44d7  xor     r8d, r8d
0x1800e44da  mov     rdx, [rbp+47h+var_48]
0x1800e44de  call    ??$_Traits_find@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K101@Z; std::_Traits_find<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800e44e3  cmp     rax, r14
0x1800e44e6  jz      loc_1800E533E
0x1800e44ec  imul    r13, r15, 88h
0x1800e44f3  add     r13, 100h
0x1800e44fa  add     r13, rsi
0x1800e44fd  lea     rax, aProcess; "process"
0x1800e4504  mov     [rbp+47h+var_A0], rax
0x1800e4508  mov     [rbp+47h+var_98], 7
0x1800e4510  lea     r8, [rbp+47h+var_A0]
0x1800e4514  lea     rdx, [rbp+47h+var_68]
0x1800e4518  mov     rcx, rdi
0x1800e451b  call    ?CreateElement@XmlWriterFacade@Diagnostics@Microsoft@@QEAA?AVXmlWriterAutoElement@23@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::XmlWriterFacade::CreateElement(std::wstring_view)
0x1800e4520  nop
0x1800e4521  lea     rax, aIdentifyinginf; "identifyinginfo"
0x1800e4528  mov     [rbp+47h+var_A0], rax
0x1800e452c  mov     [rbp+47h+var_98], 0Fh
0x1800e4534  lea     r8, [rbp+47h+var_A0]
0x1800e4538  lea     rdx, [rbp+47h+var_90]
0x1800e453c  mov     rcx, rdi
0x1800e453f  call    ?CreateElement@XmlWriterFacade@Diagnostics@Microsoft@@QEAA?AVXmlWriterAutoElement@23@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::XmlWriterFacade::CreateElement(std::wstring_view)
0x1800e4544  nop
0x1800e4545  lea     rax, aImagename; "ImageName"
0x1800e454c  mov     [rbp+47h+var_A0], rax
0x1800e4550  mov     [rbp+47h+var_98], 9
0x1800e4558  lea     rax, aInfo_0; "info"
0x1800e455f  mov     [rsp+110h+var_D0], rax
0x1800e4564  mov     [rsp+110h+var_C8], 4
0x1800e456d  lea     r9, [rbp+47h+var_58]
0x1800e4571  lea     r8, [rbp+47h+var_A0]
0x1800e4575  lea     rdx, [rsp+110h+var_D0]
0x1800e457a  mov     rcx, rdi
0x1800e457d  call    ??$WriteInfoElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<std::wstring>(std::wstring_view,std::wstring_view,std::wstring const &,bool)
0x1800e4582  xor     r15d, r15d
0x1800e4585  cmp     [r13+38h], r15d
0x1800e4589  jbe     short loc_1800E45E6
0x1800e458b  mov     ecx, [r13+38h]
0x1800e458f  add     rcx, r13
0x1800e4592  mov     [rsp+110h+var_D0], rcx
0x1800e4597  inc     r14
0x1800e459a  cmp     [rcx+r14*2], r15w
0x1800e459f  jnz     short loc_1800E4597
0x1800e45a1  mov     [rsp+110h+var_C8], r14
0x1800e45a6  lea     rax, aPackagefullnam_0; "PackageFullName"
0x1800e45ad  mov     [rbp+47h+var_A0], rax
0x1800e45b1  mov     [rbp+47h+var_98], 0Fh
0x1800e45b9  lea     r14, aInfo_0; "info"
0x1800e45c0  mov     [rsp+110h+var_E0], r14
0x1800e45c5  mov     [rsp+110h+var_D8], 4
0x1800e45ce  lea     r9, [rsp+110h+var_D0]
0x1800e45d3  lea     r8, [rbp+47h+var_A0]
0x1800e45d7  lea     rdx, [rsp+110h+var_E0]
0x1800e45dc  mov     rcx, rdi
0x1800e45df  call    ??$WriteInfoElement@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBV34@_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<std::wstring_view>(std::wstring_view,std::wstring_view,std::wstring_view const &,bool)
0x1800e45e4  jmp     short loc_1800E45ED
0x1800e45e6  lea     r14, aInfo_0; "info"
0x1800e45ed  lea     rcx, [rbp+47h+var_90]; this
0x1800e45f1  call    ??1XmlWriterAutoElement@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement(void)
0x1800e45f6  lea     rax, aSvchostExe; "svchost.exe"
0x1800e45fd  mov     [rsp+110h+var_E0], rax
0x1800e4602  mov     [rsp+110h+var_D8], 0Bh
0x1800e460b  lea     rdx, [rsp+110h+var_D0]
0x1800e4610  lea     rcx, [rbp+47h+var_58]
0x1800e4614  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800e4619  movups  xmm0, xmmword ptr [rax]
0x1800e461c  movdqu  [rbp+47h+var_90], xmm0
0x1800e4621  lea     rdx, [rsp+110h+var_E0]
0x1800e4626  lea     rcx, [rbp+47h+var_90]
0x1800e462a  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x1800e462f  test    eax, eax
0x1800e4631  jnz     loc_1800E46EE
0x1800e4637  lea     rax, aServiceinfo; "serviceinfo"
0x1800e463e  mov     [rsp+110h+var_E0], rax
0x1800e4643  mov     [rsp+110h+var_D8], 0Bh
0x1800e464c  lea     r8, [rsp+110h+var_E0]
0x1800e4651  lea     rdx, [rbp+47h+var_90]
0x1800e4655  mov     rcx, rdi
0x1800e4658  call    ?CreateElement@XmlWriterFacade@Diagnostics@Microsoft@@QEAA?AVXmlWriterAutoElement@23@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::XmlWriterFacade::CreateElement(std::wstring_view)
0x1800e465d  nop
0x1800e465e  lea     rcx, [rbp+47h+var_80]; void *
0x1800e4662  call    ??$?0AEBV?$allocator@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>(std::allocator<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>> const &)
0x1800e4667  nop
0x1800e4668  lea     rdx, [rbp+47h+var_80]
0x1800e466c  mov     ecx, [rsi+50h]
0x1800e466f  call    ?EnumerateServicesInProcess@Os@Utils@Diagnostics@Microsoft@@SAJKAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@Z; Microsoft::Diagnostics::Utils::Os::EnumerateServicesInProcess(ulong,std::vector<std::wstring> &)
0x1800e4674  mov     [rbp+47h+var_C0], eax
0x1800e4677  test    eax, eax
0x1800e4679  js      loc_1800E536F
0x1800e467f  mov     r15, [rbp+47h+var_78]
0x1800e4683  mov     rbx, [rbp+47h+var_80]
0x1800e4687  cmp     rbx, r15
0x1800e468a  jz      short loc_1800E46D8
0x1800e468c  lea     r14, aServicename; "ServiceName"
0x1800e4693  lea     r12, aInfo_0; "info"
0x1800e469a  mov     [rsp+110h+var_E0], r14
0x1800e469f  mov     [rsp+110h+var_D8], 0Bh
0x1800e46a8  mov     [rsp+110h+var_D0], r12
0x1800e46ad  mov     [rsp+110h+var_C8], 4
0x1800e46b6  mov     r9, rbx
0x1800e46b9  lea     r8, [rsp+110h+var_E0]
0x1800e46be  lea     rdx, [rsp+110h+var_D0]
0x1800e46c3  mov     rcx, rdi
0x1800e46c6  call    ??$WriteInfoElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<std::wstring>(std::wstring_view,std::wstring_view,std::wstring const &,bool)
0x1800e46cb  add     rbx, 20h ; ' '
0x1800e46cf  cmp     rbx, r15
0x1800e46d2  jnz     short loc_1800E469A
0x1800e46d4  lea     r12, [rsi+4]
0x1800e46d8  xor     r15d, r15d
0x1800e46db  lea     rcx, [rbp+47h+var_80]
0x1800e46df  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800e46e4  nop
0x1800e46e5  lea     rcx, [rbp+47h+var_90]; this
0x1800e46e9  call    ??1XmlWriterAutoElement@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement(void)
0x1800e46ee  lea     rax, aPerformanceinf; "performanceinfo"
0x1800e46f5  mov     [rsp+110h+var_E0], rax
0x1800e46fa  mov     ebx, 0Fh
0x1800e46ff  mov     [rsp+110h+var_D8], rbx
0x1800e4704  lea     r8, [rsp+110h+var_E0]
0x1800e4709  lea     rdx, [rbp+47h+var_90]
0x1800e470d  mov     rcx, rdi
0x1800e4710  call    ?CreateElement@XmlWriterFacade@Diagnostics@Microsoft@@QEAA?AVXmlWriterAutoElement@23@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::XmlWriterFacade::CreateElement(std::wstring_view)
0x1800e4715  nop
0x1800e4716  lea     rax, aNumberofthread_0; "NumberOfThreads"
0x1800e471d  mov     [rsp+110h+var_E0], rax
0x1800e4722  mov     [rsp+110h+var_D8], rbx
0x1800e4727  lea     rbx, aInfo_0; "info"
0x1800e472e  mov     [rsp+110h+var_D0], rbx
0x1800e4733  mov     r14d, 4
0x1800e4739  mov     [rsp+110h+var_C8], r14
0x1800e473e  mov     byte ptr [rsp+110h+var_F0], r15b
0x1800e4743  mov     r9, r12
0x1800e4746  lea     r8, [rsp+110h+var_E0]
0x1800e474b  lea     rdx, [rsp+110h+var_D0]
0x1800e4750  mov     rcx, rdi
0x1800e4753  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x1800e4758  lea     rax, aWorkingsetpriv; "WorkingSetPrivateSize"
0x1800e475f  mov     [rsp+110h+var_E0], rax
0x1800e4764  mov     [rsp+110h+var_D8], 15h
0x1800e476d  mov     [rsp+110h+var_D0], rbx
0x1800e4772  mov     [rsp+110h+var_C8], r14
0x1800e4777  lea     r9, [rsi+8]
0x1800e477b  lea     r8, [rsp+110h+var_E0]
0x1800e4780  lea     rdx, [rsp+110h+var_D0]
0x1800e4785  mov     rcx, rdi
0x1800e4788  call    ??$WriteInfoElement@_J@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_J_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(std::wstring_view,std::wstring_view,__int64 const &,bool)
0x1800e478d  lea     rax, aHardfaultcount; "HardFaultCount"
0x1800e4794  mov     [rsp+110h+var_E0], rax
0x1800e4799  mov     r14d, 0Eh
0x1800e479f  mov     [rsp+110h+var_D8], r14
0x1800e47a4  mov     [rsp+110h+var_D0], rbx
0x1800e47a9  mov     [rsp+110h+var_C8], 4
0x1800e47b2  lea     r9, [rsi+10h]
0x1800e47b6  mov     byte ptr [rsp+110h+var_F0], r15b
0x1800e47bb  lea     r8, [rsp+110h+var_E0]
0x1800e47c0  lea     rdx, [rsp+110h+var_D0]
0x1800e47c5  mov     rcx, rdi
0x1800e47c8  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x1800e47cd  lea     rax, aNumberofthread; "NumberOfThreadsHighWatermark"
0x1800e47d4  mov     [rsp+110h+var_E0], rax
0x1800e47d9  lea     ebx, [r14+0Eh]
0x1800e47dd  mov     [rsp+110h+var_D8], rbx
0x1800e47e2  lea     rax, aInfo_0; "info"
0x1800e47e9  mov     [rsp+110h+var_D0], rax
0x1800e47ee  mov     [rsp+110h+var_C8], 4
0x1800e47f7  lea     r9, [rsi+14h]
0x1800e47fb  mov     byte ptr [rsp+110h+var_F0], r15b
0x1800e4800  lea     r8, [rsp+110h+var_E0]
0x1800e4805  lea     rdx, [rsp+110h+var_D0]
0x1800e480a  mov     rcx, rdi
0x1800e480d  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x1800e4812  lea     rax, aCycletime; "CycleTime"
0x1800e4819  mov     [rsp+110h+var_E0], rax
0x1800e481e  mov     [rsp+110h+var_D8], 9
0x1800e4827  lea     rax, aInfo_0; "info"
0x1800e482e  mov     [rsp+110h+var_D0], rax
0x1800e4833  mov     [rsp+110h+var_C8], 4
0x1800e483c  lea     r9, [rsi+18h]
0x1800e4840  mov     byte ptr [rsp+110h+var_F0], r15b
0x1800e4845  lea     r8, [rsp+110h+var_E0]
0x1800e484a  lea     rdx, [rsp+110h+var_D0]
0x1800e484f  mov     rcx, rdi
0x1800e4852  call    ??$WriteInfoElement@_K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_K_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(std::wstring_view,std::wstring_view,unsigned __int64 const &,bool)
0x1800e4857  lea     rax, aCreatetime; "CreateTime"
0x1800e485e  mov     [rsp+110h+var_E0], rax
0x1800e4863  mov     [rsp+110h+var_D8], 0Ah
0x1800e486c  lea     rax, aInfo_0; "info"
0x1800e4873  mov     [rsp+110h+var_D0], rax
0x1800e4878  mov     [rsp+110h+var_C8], 4
0x1800e4881  lea     r9, [rsi+20h]
0x1800e4885  lea     r8, [rsp+110h+var_E0]
0x1800e488a  lea     rdx, [rsp+110h+var_D0]
0x1800e488f  mov     rcx, rdi
0x1800e4892  call    ??$WriteInfoElement@_J@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_J_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(std::wstring_view,std::wstring_view,__int64 const &,bool)
0x1800e4897  lea     rax, aUsertime; "UserTime"
0x1800e489e  mov     [rsp+110h+var_E0], rax
0x1800e48a3  mov     [rsp+110h+var_D8], 8
0x1800e48ac  lea     rax, aInfo_0; "info"
0x1800e48b3  mov     [rsp+110h+var_D0], rax
0x1800e48b8  mov     [rsp+110h+var_C8], 4
0x1800e48c1  lea     r9, [rsi+28h]
0x1800e48c5  lea     r8, [rsp+110h+var_E0]
0x1800e48ca  lea     rdx, [rsp+110h+var_D0]
0x1800e48cf  mov     rcx, rdi
0x1800e48d2  call    ??$WriteInfoElement@_J@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_J_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(std::wstring_view,std::wstring_view,__int64 const &,bool)
0x1800e48d7  lea     rax, aKerneltime; "KernelTime"
0x1800e48de  mov     [rsp+110h+var_E0], rax
0x1800e48e3  mov     [rsp+110h+var_D8], 0Ah
0x1800e48ec  lea     rax, aInfo_0; "info"
0x1800e48f3  mov     [rsp+110h+var_D0], rax
0x1800e48f8  mov     [rsp+110h+var_C8], 4
0x1800e4901  lea     r9, [rsi+30h]
0x1800e4905  lea     r8, [rsp+110h+var_E0]
0x1800e490a  lea     rdx, [rsp+110h+var_D0]
0x1800e490f  mov     rcx, rdi
0x1800e4912  call    ??$WriteInfoElement@_J@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_J_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(std::wstring_view,std::wstring_view,__int64 const &,bool)
0x1800e4917  lea     rax, aBasepriority; "BasePriority"
0x1800e491e  mov     [rsp+110h+var_E0], rax
0x1800e4923  mov     [rsp+110h+var_D8], 0Ch
0x1800e492c  lea     rax, aInfo_0; "info"
0x1800e4933  mov     [rsp+110h+var_D0], rax
0x1800e4938  mov     [rsp+110h+var_C8], 4
0x1800e4941  lea     r9, [rsi+48h]
0x1800e4945  lea     r8, [rsp+110h+var_E0]
0x1800e494a  lea     rdx, [rsp+110h+var_D0]
0x1800e494f  mov     rcx, rdi
0x1800e4952  call    ??$WriteInfoElement@J@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBJ_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<long>(std::wstring_view,std::wstring_view,long const &,bool)
0x1800e4957  mov     rax, [rsi+50h]
0x1800e495b  mov     [rbp+47h+var_B0], rax
0x1800e495f  lea     rax, aUniqueprocessi; "UniqueProcessId"
0x1800e4966  mov     [rsp+110h+var_E0], rax
0x1800e496b  mov     [rsp+110h+var_D8], 0Fh
0x1800e4974  lea     rax, aInfo_0; "info"
0x1800e497b  mov     [rsp+110h+var_D0], rax
0x1800e4980  mov     [rsp+110h+var_C8], 4
0x1800e4989  mov     byte ptr [rsp+110h+var_F0], r15b
0x1800e498e  lea     r9, [rbp+47h+var_B0]
0x1800e4992  lea     r8, [rsp+110h+var_E0]
0x1800e4997  lea     rdx, [rsp+110h+var_D0]
0x1800e499c  mov     rcx, rdi
0x1800e499f  call    ??$WriteInfoElement@_K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_K_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(std::wstring_view,std::wstring_view,unsigned __int64 const &,bool)
0x1800e49a4  mov     rax, [rsi+58h]
0x1800e49a8  mov     [rbp+47h+var_B0], rax
0x1800e49ac  lea     rax, aInheritedfromu; "InheritedFromUniqueProcessId"
0x1800e49b3  mov     [rsp+110h+var_E0], rax
0x1800e49b8  mov     [rsp+110h+var_D8], rbx
0x1800e49bd  lea     rbx, aInfo_0; "info"
0x1800e49c4  mov     [rsp+110h+var_D0], rbx
0x1800e49c9  mov     [rsp+110h+var_C8], 4
0x1800e49d2  mov     byte ptr [rsp+110h+var_F0], r15b
0x1800e49d7  lea     r9, [rbp+47h+var_B0]
0x1800e49db  lea     r8, [rsp+110h+var_E0]
0x1800e49e0  lea     rdx, [rsp+110h+var_D0]
0x1800e49e5  mov     rcx, rdi
0x1800e49e8  call    ??$WriteInfoElement@_K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_K_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(std::wstring_view,std::wstring_view,unsigned __int64 const &,bool)
  ... truncated ...
```
