# CSecurityManager::MapSpecialShellProtocols(ZONEMAP_COMPONENTS *,ulong *,ulong,TRIBIT *,ushort * *)

- ea: `0x18010ae70`
- end: `0x18010bcf3`
- name: `?MapSpecialShellProtocols@CSecurityManager@@IEAA_NPEAVZONEMAP_COMPONENTS@@PEAKKPEAW4TRIBIT@@PEAPEAG@Z`
- size: `3715`
- prototype: `bool __usercall@<al>(CSecurityManager *__hidden this@<rcx>, struct ZONEMAP_COMPONENTS *@<rdx>, unsigned int *@<r8>, unsigned int@<r9d>, enum TRIBIT *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800a03ec`

## callees

- `0x18001cb00`
- `0x18003e100`
- `0x18003e540`
- `0x180080488`
- `0x1800a07e0`
- `0x18010ae70`
- `0x18010dc04`
- `0x1801285fe`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18010bb23`
- `msvcrt!wcsncpy_s` at `0x18010bb23`
- `msvcrt!wcschr` at `0x18010baef`
- `msvcrt!wcschr` at `0x18010baef`
- `msvcrt!wcscat_s` at `0x18010bbda`
- `msvcrt!wcscat_s` at `0x18010bbda`
- `msvcrt!wcscpy_s` at `0x18010bad9`
- `msvcrt!wcscpy_s` at `0x18010bb3b`
- `msvcrt!wcscpy_s` at `0x18010bb49`
- `msvcrt!wcscpy_s` at `0x18010bbbe`
- `msvcrt!wcscpy_s` at `0x18010bad9`
- `msvcrt!wcscpy_s` at `0x18010bb3b`
- `msvcrt!wcscpy_s` at `0x18010bb49`
- `msvcrt!wcscpy_s` at `0x18010bbbe`
- `iertutil!CreateUri` at `0x18010bc22`
- `iertutil!CreateUri` at `0x18010bc22`
- `api-ms-win-shell-namespace-l1-1-0!SHParseDisplayName` at `0x18010bb75`
- `api-ms-win-shell-namespace-l1-1-0!SHParseDisplayName` at `0x18010bb75`
- `SHELL32!SHGetPathFromIDListW` at `0x18010bb95`
- `SHELL32!SHGetPathFromIDListW` at `0x18010bb95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010bcb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010bcb9`

## string_xrefs

- `0x18010af0a`: `Cache`
- `0x18010aeff`: `AppUpdatesFolder`
- `0x18010af20`: `ChangeRemoveProgramsFolder`
- `0x18010af36`: `Common AppData`
- `0x18010af2b`: `Common Administrative Tools`
- `0x18010af4c`: `Common Documents`
- `0x18010af41`: `Common Desktop`
- `0x18010af62`: `Common Start Menu`
- `0x18010af57`: `Common Programs`
- `0x18010af78`: `Common Templates`
- `0x18010af6d`: `Common Startup`
- `0x18010af8e`: `CommonMusic`
- `0x18010af83`: `CommonDownloads`
- `0x18010afa4`: `CommonRingtones`
- `0x18010af99`: `CommonPictures`
- `0x18010afaf`: `CommonVideo`
- `0x18010b06d`: `GameTasks`
- `0x18010b0c1`: `Links`
- `0x18010b13f`: `MyComputerFolder`
- `0x18010b15b`: `OEM Links`
- `0x18010b1f5`: `ProgramFilesCommonX86`
- `0x18010b1e7`: `ProgramFilesCommon`
- `0x18010b23b`: `PublicGameTasks`
- `0x18010b37d`: `Templates`
- `0x18010b3b5`: `UserProgramFilesCommon`

## pseudocode

```c
char __fastcall CSecurityManager::MapSpecialShellProtocols(
        CSecurityManager *this,
        struct ZONEMAP_COMPONENTS *a2,
        unsigned int *a3,
        __int64 a4,
        enum TRIBIT *a5,
        unsigned __int16 **a6)
{
  const unsigned __int16 *v9; // r8
  char v10; // si
  const wchar_t *v11; // r8
  wchar_t *v12; // rax
  const wchar_t *v13; // rbx
  DWORD v14; // eax
  IUri *v15; // rdi
  unsigned int v16; // r8d
  IUri *v17; // rbx
  LPITEMIDLIST ppidl; // [rsp+30h] [rbp-D0h] BYREF
  IUri *ppURI; // [rsp+38h] [rbp-C8h] BYREF
  IUri *ppSecUri; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v22[226]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Destination[264]; // [rsp+760h] [rbp+660h] BYREF
  wchar_t pszName[264]; // [rsp+970h] [rbp+870h] BYREF
  wchar_t Source[264]; // [rsp+B80h] [rbp+A80h] BYREF
  wchar_t pwzURI[264]; // [rsp+D90h] [rbp+C90h] BYREF

  v22[0] = L"AccountPictures";
  v22[1] = L"AddNewProgramsFolder";
  v22[2] = L"Administrative Tools";
  v22[3] = L"AppData";
  v22[4] = L"Application Shortcuts";
  v22[5] = L"AppsFolder";
  v22[6] = L"AppUpdatesFolder";
  v22[7] = L"Cache";
  v22[8] = L"CD Burning";
  v22[9] = L"ChangeRemoveProgramsFolder";
  v22[10] = L"Common Administrative Tools";
  v22[11] = L"Common AppData";
  v22[12] = L"Common Desktop";
  v22[13] = L"Common Documents";
  v22[14] = L"Common Programs";
  v22[15] = L"Common Start Menu";
  v22[16] = L"Common Startup";
  v22[17] = L"Common Templates";
  v22[18] = L"CommonDownloads";
  v22[19] = L"CommonMusic";
  v22[20] = L"CommonPictures";
  v22[21] = L"CommonRingtones";
  v22[22] = L"CommonVideo";
  v22[23] = L"ConflictFolder";
  v22[24] = L"ConnectionsFolder";
  v22[25] = L"Contacts";
  v22[26] = L"ControlPanelFolder";
  v22[27] = L"Cookies";
  v22[28] = L"CredentialManager";
  v22[29] = L"CryptoKeys";
  v22[30] = L"CSCFolder";
  v22[31] = L"Desktop";
  v22[32] = L"Device Metadata Store";
  v22[33] = L"DocumentsLibrary";
  v22[34] = L"Downloads";
  v22[35] = L"DpapiKeys";
  v22[36] = L"Favorites";
  v22[37] = L"Fonts";
  v22[38] = L"Games";
  v22[39] = L"GameTasks";
  v22[40] = L"History";
  v22[41] = L"HomeGroupCurrentUserFolder";
  v22[42] = L"HomeGroupFolder";
  v22[43] = L"ImplicitAppShortcuts";
  v22[44] = L"Libraries";
  v22[45] = L"Links";
  v22[46] = L"Local AppData";
  v22[47] = L"LocalAppDataLow";
  v22[48] = L"LocalizedResourcesDir";
  v22[49] = L"MAPIFolder";
  v22[50] = L"MusicLibrary";
  v22[51] = L"My Music";
  v22[52] = L"My Pictures";
  v22[53] = L"My Video";
  v22[54] = L"MyComputerFolder";
  v22[55] = L"NetHood";
  v22[56] = L"OEM Links";
  v22[57] = L"Original Images";
  v22[58] = L"Personal";
  v22[59] = L"PhotoAlbums";
  v22[60] = L"PicturesLibrary";
  v22[61] = L"Playlists";
  v22[62] = L"PrintersFolder";
  v22[63] = L"PrintHood";
  v22[64] = L"Profile";
  v22[65] = L"ProgramFiles";
  v22[66] = L"ProgramFilesCommon";
  v22[67] = L"ProgramFilesCommonX86";
  v22[68] = L"ProgramFilesX86";
  v22[69] = L"Programs";
  v22[70] = L"Public";
  v22[71] = L"PublicAccountPictures";
  v22[72] = L"PublicGameTasks";
  v22[73] = L"PublicLibraries";
  v22[74] = L"Quick Launch";
  v22[75] = L"Recent";
  v22[76] = L"RecordedTVLibrary";
  v22[77] = L"RecycleBinFolder";
  v22[78] = L"ResourceDir";
  v22[79] = L"Ringtones";
  v22[80] = L"Roamed Tile Images";
  v22[81] = L"Roaming Tiles";
  v22[82] = L"SavedGames";
  v22[83] = L"Screenshots";
  v22[84] = L"Searches";
  v22[85] = L"SearchHomeFolder";
  v22[86] = L"SendTo";
  v22[87] = L"Start Menu";
  v22[88] = L"Startup";
  v22[89] = L"SyncCenterFolder";
  v22[90] = L"SyncResultsFolder";
  v22[91] = L"SyncSetupFolder";
  v22[92] = L"System";
  v22[93] = L"SystemCertificates";
  v22[94] = L"SystemX86";
  v22[95] = L"Templates";
  v22[96] = L"User Pinned";
  v22[97] = L"UserProfiles";
  v22[98] = L"UserProgramFiles";
  v22[99] = L"UserProgramFilesCommon";
  v22[100] = L"UsersFilesFolder";
  v22[101] = L"UsersLibrariesFolder";
  v22[102] = L"VideosLibrary";
  v22[103] = L"Windows";
  v22[104] = L"{008ca0b1-55b4-4c56-b8a8-4de4b299d3be}";
  v22[105] = L"{00BCFC5A-ED94-4e48-96A1-3F6217F21990}";
  v22[106] = L"{0139D44E-6AFE-49F2-8690-3DAFCAE6FFB8}";
  v22[107] = L"{0482af6c-08f1-4c34-8c90-e17ec98b1e17}";
  v22[108] = L"{054FAE61-4DD8-4787-80B6-090220C4B700}";
  v22[109] = L"{0762D272-C50A-4BB0-A382-697DCD729B80}";
  v22[110] = L"{0AC0837C-BBF8-452A-850D-79D08E667CA7}";
  v22[111] = L"{0D4C3DB6-03A3-462F-A0E6-08924C41B5D4}";
  v22[112] = L"{0F214138-B1D3-4a90-BBA9-27CBC0C5389A}";
  v22[113] = L"{15CA69B3-30EE-49C1-ACE1-6B5EC372AFB5}";
  v22[114] = L"{1777F761-68AD-4D8A-87BD-30B759FA33DD}";
  v22[115] = L"{18989B1D-99B5-455B-841C-AB7C74E4DDFC}";
  v22[116] = L"{190337d1-b8ca-4121-a639-6d472d16972a}";
  v22[117] = L"{1A6FDBA2-F42D-4358-A798-B74D745926C5}";
  v22[118] = L"{1AC14E77-02E7-4E5D-B744-2EB1AE5198B7}";
  v22[119] = L"{1B3EA5DC-B587-4786-B4EF-BD1DC332AEAE}";
  v22[120] = L"{1e87508d-89c2-42f0-8a7e-645a0f50ca58}";
  v22[121] = L"{2112AB0A-C86A-4FFE-A368-0DE96E47012E}";
  v22[122] = L"{2400183A-6185-49FB-A2D8-4A392A602BA3}";
  v22[123] = L"{24D89E24-2F19-4534-9DDE-6A6671FBB8FE}";
  v22[124] = L"{289a9a43-be44-4057-a41b-587a76d7e7f9}";
  v22[125] = L"{2A00375E-224C-49DE-B8D1-440DF7EF3DDC}";
  v22[126] = L"{2B0F765D-C0E9-4171-908E-08A611B84FF6}";
  v22[127] = L"{2C36C0AA-5812-4b87-BFD0-4CD0DFB19B39}";
  v22[128] = L"{31C0DD25-9439-4F12-BF41-7FF4EDA38722}";
  v22[129] = L"{3214FAB5-9757-4298-BB61-92A9DEAA44FF}";
  v22[130] = L"{339719B5-8C47-4894-94C2-D8F77ADD44A6}";
  v22[131] = L"{33E28130-4E1E-4676-835A-98395C3BC3BB}";
  v22[132] = L"{352481E8-33BE-4251-BA85-6007CAEDCF9D}";
  v22[133] = L"{374DE290-123F-4565-9164-39C4925E467B}";
  v22[134] = L"{3B193882-D3AD-4eab-965A-69829D1FB59F}";
  v22[135] = L"{3D644C9B-1FB8-4f30-9B45-F670235F79C0}";
  v22[136] = L"{3EB685DB-65F9-4CF6-A03A-E3EF65729F3D}";
  v22[137] = L"{43668BF8-C14E-49B2-97C9-747784D784B7}";
  v22[138] = L"{48DAF80B-E6CF-4F4E-B800-0E69D84EE384}";
  v22[139] = L"{491E922F-5643-4AF4-A7EB-4E7A138D8174}";
  v22[140] = L"{4BD8D571-6D19-48D3-BE97-422220080E43}";
  v22[141] = L"{4bfefb45-347d-4006-a5be-ac0cb0567192}";
  v22[142] = L"{4C5C32FF-BB9D-43b0-B5B4-2D72E54EAAA4}";
  v22[143] = L"{52528A6B-B9E3-4ADD-B60D-588C2DBA842D}";
  v22[144] = L"{52a4f021-7b75-48a9-9f6b-4b87a210bc8f}";
  v22[145] = L"{559D40A3-A036-40FA-AF61-84CB430A4D34}";
  v22[146] = L"{56784854-C6CB-462b-8169-88E350ACB882}";
  v22[147] = L"{5CD7AEE2-2219-4A67-B85D-6C9CE15660CB}";
  v22[148] = L"{5CE4A5E9-E4EB-479D-B89F-130C02886155}";
  v22[149] = L"{5E6C858F-0E22-4760-9AFE-EA3317B67173}";
  v22[150] = L"{625B53C3-AB48-4EC1-BA1F-A1EF4146FC19}";
  v22[151] = L"{62AB5D82-FDC1-4DC3-A9DD-070D1D495D97}";
  v22[152] = L"{6365D5A7-0F0D-45E5-87F6-0DA56B6A4F7D}";
  v22[153] = L"{69D2CF90-FC33-4FB7-9A0C-EBB0F0FCB43C}";
  v22[154] = L"{6D809377-6AF0-444b-8957-A3773F02200E}";
  v22[155] = L"{6F0CD92B-2E97-45D1-88FF-B0D186B8DEDD}";
  v22[156] = L"{724EF170-A42D-4FEF-9F26-B60E846FBA4F}";
  v22[157] = L"{767E6811-49CB-4273-87C2-20F355E1085B}";
  v22[158] = L"{76FC4E2D-D6AD-4519-A663-37BD56068185}";
  v22[159] = L"{7B0DB17D-9CD2-4A93-9733-46CC89022E7C}";
  v22[160] = L"{7B396E54-9EC5-4300-BE0A-2482EBAE1A26}";
  v22[161] = L"{7BE16610-1F7F-44AC-BFF0-83E15F2FFCA1}";
  v22[162] = L"{7C5A40EF-A0FB-4BFC-874A-C0F2E0B9FA8E}";
  v22[163] = L"{7CFBEFBC-DE1F-45AA-B843-A542AC536CC9}";
  v22[164] = L"{7d1d3a04-debb-4115-95cf-2f29da2920da}";
  v22[165] = L"{7E636BFE-DFA9-4D5E-B456-D7B39851D8A9}";
  v22[166] = L"{82A5EA35-D9CD-47C5-9629-E15D2F714E6E}";
  v22[167] = L"{82A74AEB-AEB4-465C-A014-D097EE346D63}";
  v22[168] = L"{859EAD94-2E85-48AD-A71A-0969CB56A6CD}";
  v22[169] = L"{8983036C-27C0-404B-8F08-102D10DCFD74}";
  v22[170] = L"{8AD10C31-2ADB-4296-A8F7-E4701232C972}";
  v22[171] = L"{905e63b6-c1bf-494e-b29c-65b732d3d21a}";
  v22[172] = L"{9274BD8D-CFD1-41C3-B35E-B13F55A758F4}";
  v22[173] = L"{98ec0e18-2098-4d44-8644-66979315a281}";
  v22[174] = L"{9B74B6A3-0DFD-4f11-9E78-5F7800F2E772}";
  v22[175] = L"{9E3995AB-1F9C-4F13-B827-48B24B6C7174}";
  v22[176] = L"{9E52AB10-F80D-49DF-ACB8-4330F5687855}";
  v22[177] = L"{A302545D-DEFF-464b-ABE8-61C8648D939B}";
  v22[178] = L"{a305ce99-f527-492b-8b1a-7e76fa98d6e4}";
  v22[179] = L"{A3918781-E5F2-4890-B3D9-A7E54332328C}";
  v22[180] = L"{A4115719-D62E-491D-AA7C-E74B8BE3B067}";
  v22[181] = L"{A520A1A4-1780-4FF6-BD18-167343C5AF16}";
  v22[182] = L"{A52BBA46-E9E1-435f-B3D9-28DAA648C0F6}";
  v22[183] = L"{A63293E8-664E-48DB-A079-DF759E0509F7}";
  v22[184] = L"{A75D362E-50FC-4fb7-AC2C-A8BEAA314493}";
  v22[185] = L"{A77F5D77-2E2B-44C3-A6A2-ABA601054A51}";
  v22[186] = L"{A990AE9F-A03B-4E80-94BC-9912D7504104}";
  v22[187] = L"{AAA8D5A5-F1D6-4259-BAA8-78E7EF60835E}";
  v22[188] = L"{AB5FB87B-7CE2-4F83-915D-550846C9537B}";
  v22[189] = L"{AE50C081-EBD2-438A-8655-8A092E34987A}";
  v22[190] = L"{B250C668-F57D-4EE1-A63C-290EE7D1AA1F}";
  v22[191] = L"{B2C5E279-7ADD-439F-B28C-C41FE1BBF672}";
  v22[192] = L"{B4BFCC3A-DB2C-424C-B029-7FE99A87C641}";
  v22[193] = L"{B6EBFB86-6907-413C-9AF7-4FC2ABF07CC5}";
  v22[194] = L"{B7534046-3ECB-4C18-BE4E-64CD4CB7D6AC}";
  v22[195] = L"{b7bede81-df94-4682-a7d8-57a52620b86f}";
  v22[196] = L"{B94237E7-57AC-4347-9151-B08C6C32D1F7}";
  v22[197] = L"{B97D20BB-F46A-4C97-BA10-5E3608430854}";
  v22[198] = L"{BCB5256F-79F6-4CEE-B725-DC34E402FD46}";
  v22[199] = L"{BCBD3057-CA5C-4622-B42D-BC56DB0AE516}";
  v9 = (const unsigned __int16 *)*((_QWORD *)a2 + 2);
  v22[200] = L"{bfb9d5e0-c6a9-404c-b2b2-ae6db6af4968}";
  v22[201] = L"{C1BAE2D0-10DF-4334-BEDD-7AA20B227A9D}";
  v10 = 0;
  v22[202] = L"{C4900540-2379-4C75-844B-64E6FAF8716B}";
  v22[203] = L"{C4AA340D-F20F-4863-AFEF-F87EF2E6BA25}";
  v22[204] = L"{C5ABBF53-E17F-4121-8900-86626FC2C973}";
  v22[205] = L"{C870044B-F49E-4126-A9C3-B52A1FF411E8}";
  v22[206] = L"{CAC52C1A-B53D-4edc-92D7-6B2E8AC19434}";
  v22[207] = L"{D0384E7D-BAC3-4797-8F14-CBA229B392B5}";
  v22[208] = L"{D65231B0-B2F1-4857-A4CE-A8E7C6EA7D27}";
  v22[209] = L"{D9DC8A3B-B784-432E-A781-5A1130A75963}";
  v22[210] = L"{de61d971-5ebc-4f02-a3a9-6c82895e5c04}";
  v22[211] = L"{DE92C1C7-837F-4F69-A3BB-86E631204A23}";
  v22[212] = L"{DE974D24-D9C6-4D3E-BF91-F4455120B917}";
  v22[213] = L"{DEBF2536-E1A8-4c59-B6A2-414586476AEA}";
  v22[214] = L"{df7266ac-9274-4867-8d55-3bd661de872d}";
  v22[215] = L"{DFDF76A2-C82A-4D63-906A-5644AC457385}";
  v22[216] = L"{E25B5812-BE88-4bd9-94B0-29233477B6C3}";
  v22[217] = L"{E555AB60-153B-4D17-9F04-A5FE99FC15EC}";
  v22[218] = L"{ED4824AF-DCE4-45A8-81E2-FC7965083634}";
  v22[219] = L"{ee32e446-31ca-4aba-814f-a5ebd2fd6d5e}";
  v22[220] = L"{F1B32785-6FBA-4FCF-9D55-7B8E7F157091}";
  v22[221] = L"{F38BF404-1D43-42F2-9305-67DE0B28FC23}";
  v22[222] = L"{f3ce0f7c-4901-4acc-8648-d5d44b04ef8f}";
  v22[223] = L"{F7F1ED05-9F6D-47A2-AAAE-29D317C6F066}";
  v22[224] = L"{FD228CB7-AE11-4AE3-864C-16F3910AB8FE}";
  v22[225] = L"{FDD39AD0-238F-46AF-ADB4-6C85480369C7}";
  if ( binarySearch((const unsigned __int16 **const)v22, (unsigned __int64)a2, v9) )
  {
    v11 = (const wchar_t *)*((_QWORD *)a2 + 4);
    ppidl = 0;
    wcscpy_s(Destination, 0x104u, v11);
    v12 = wcschr(Destination, 0x5Cu);
    v13 = v12;
    if ( v12 )
    {
      wcsncpy_s(pszName, 0x104u, Destination, v12 - Destination);
      wcscpy_s(Source, 0x104u, v13);
    }
    else
    {
      wcscpy_s(pszName, 0x104u, Destination);
      Source[0] = 0;
    }
    v10 = 1;
    if ( SHParseDisplayName(pszName, 0, &ppidl, 0, 0) >= 0 )
    {
      if ( SHGetPathFromIDListW(ppidl, pszName) )
      {
        wcscpy_s(pwzURI, 0x104u, pszName);
        wcscat_s(pwzURI, 0x104u, Source);
        ppURI = 0;
        ppSecUri = 0;
        memset_0(v22, 0, 0x4E8u);
        v14 = HelperAddUriDefaultFlags(0x3002B80u, 4u);
        if ( CreateUri(pwzURI, v14, 0, &ppURI) >= 0 )
        {
          v15 = ppURI;
          if ( CoInternetGetSecurityUrlEx(ppURI, &ppSecUri, PSU_DEFAULT, 0) >= 0 )
          {
            v17 = ppSecUri;
            if ( (int)ZONEMAP_COMPONENTS::Crack((ZONEMAP_COMPONENTS *)v22, ppSecUri, v16, 0) >= 0 )
            {
              *a3 = 0;
              CSecurityManager::_MapPathToZone(this, (struct ZONEMAP_COMPONENTS *)v22, a3, 0, a5, a6);
            }
            ((void (__fastcall *)(IUri *))v17->lpVtbl->Release)(v17);
          }
          ((void (__fastcall *)(IUri *))v15->lpVtbl->Release)(v15);
        }
        ZONEMAP_COMPONENTS::~ZONEMAP_COMPONENTS((ZONEMAP_COMPONENTS *)v22);
      }
      CoTaskMemFree(ppidl);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18010ae70  mov     [rsp-8+arg_18], rbx
0x18010ae75  push    rbp
0x18010ae76  push    rsi
0x18010ae77  push    rdi
0x18010ae78  push    r12
0x18010ae7a  push    r13
0x18010ae7c  push    r14
0x18010ae7e  push    r15
0x18010ae80  lea     rbp, [rsp-0EB0h]
0x18010ae88  sub     rsp, 0FB0h
0x18010ae8f  mov     rax, cs:__security_cookie
0x18010ae96  xor     rax, rsp
0x18010ae99  mov     [rbp+0EE0h+var_40], rax
0x18010aea0  mov     r12, [rbp+0EE0h+arg_20]
0x18010aea7  lea     rax, aAccountpicture; "AccountPictures"
0x18010aeae  mov     [rsp+0FE0h+var_F90], rax
0x18010aeb3  mov     r14, r8
0x18010aeb6  mov     r13, [rbp+0EE0h+arg_28]
0x18010aebd  lea     rax, aAddnewprograms; "AddNewProgramsFolder"
0x18010aec4  mov     [rsp+0FE0h+var_F88], rax
0x18010aec9  mov     rbx, rdx
0x18010aecc  lea     rax, aAdministrative; "Administrative Tools"
0x18010aed3  mov     r15, rcx
0x18010aed6  mov     [rsp+0FE0h+var_F80], rax
0x18010aedb  lea     rax, aAppdata; "AppData"
0x18010aee2  mov     [rsp+0FE0h+var_F78], rax
0x18010aee7  lea     rax, aApplicationSho; "Application Shortcuts"
0x18010aeee  mov     [rsp+0FE0h+var_F70], rax
0x18010aef3  lea     rax, aAppsfolder; "AppsFolder"
0x18010aefa  mov     [rsp+0FE0h+var_F68], rax
0x18010aeff  lea     rax, aAppupdatesfold; "AppUpdatesFolder"
0x18010af06  mov     [rbp+0EE0h+var_F60], rax
0x18010af0a  lea     rax, aCache; "Cache"
0x18010af11  mov     [rbp+0EE0h+var_F58], rax
0x18010af15  lea     rax, aCdBurning; "CD Burning"
0x18010af1c  mov     [rbp+0EE0h+var_F50], rax
0x18010af20  lea     rax, aChangeremovepr; "ChangeRemoveProgramsFolder"
0x18010af27  mov     [rbp+0EE0h+var_F48], rax
0x18010af2b  lea     rax, aCommonAdminist; "Common Administrative Tools"
0x18010af32  mov     [rbp+0EE0h+var_F40], rax
0x18010af36  lea     rax, aCommonAppdata; "Common AppData"
0x18010af3d  mov     [rbp+0EE0h+var_F38], rax
0x18010af41  lea     rax, aCommonDesktop; "Common Desktop"
0x18010af48  mov     [rbp+0EE0h+var_F30], rax
0x18010af4c  lea     rax, aCommonDocument; "Common Documents"
0x18010af53  mov     [rbp+0EE0h+var_F28], rax
0x18010af57  lea     rax, aCommonPrograms; "Common Programs"
0x18010af5e  mov     [rbp+0EE0h+var_F20], rax
0x18010af62  lea     rax, aCommonStartMen; "Common Start Menu"
0x18010af69  mov     [rbp+0EE0h+var_F18], rax
0x18010af6d  lea     rax, aCommonStartup; "Common Startup"
0x18010af74  mov     [rbp+0EE0h+var_F10], rax
0x18010af78  lea     rax, aCommonTemplate; "Common Templates"
0x18010af7f  mov     [rbp+0EE0h+var_F08], rax
0x18010af83  lea     rax, aCommondownload; "CommonDownloads"
0x18010af8a  mov     [rbp+0EE0h+var_F00], rax
0x18010af8e  lea     rax, aCommonmusic; "CommonMusic"
0x18010af95  mov     [rbp+0EE0h+var_EF8], rax
0x18010af99  lea     rax, aCommonpictures; "CommonPictures"
0x18010afa0  mov     [rbp+0EE0h+var_EF0], rax
0x18010afa4  lea     rax, aCommonringtone; "CommonRingtones"
0x18010afab  mov     [rbp+0EE0h+var_EE8], rax
0x18010afaf  lea     rax, aCommonvideo; "CommonVideo"
0x18010afb6  mov     [rbp+0EE0h+var_EE0], rax
0x18010afba  lea     rax, aConflictfolder; "ConflictFolder"
0x18010afc1  mov     [rbp+0EE0h+var_ED8], rax
0x18010afc5  lea     rax, aConnectionsfol; "ConnectionsFolder"
0x18010afcc  mov     [rbp+0EE0h+var_ED0], rax
0x18010afd0  lea     rax, aContacts; "Contacts"
0x18010afd7  mov     [rbp+0EE0h+var_EC8], rax
0x18010afdb  lea     rax, aControlpanelfo; "ControlPanelFolder"
0x18010afe2  mov     [rbp+0EE0h+var_EC0], rax
0x18010afe6  lea     rax, aCookies; "Cookies"
0x18010afed  mov     [rbp+0EE0h+var_EB8], rax
0x18010aff1  lea     rax, aCredentialmana; "CredentialManager"
0x18010aff8  mov     [rbp+0EE0h+var_EB0], rax
0x18010affc  lea     rax, aCryptokeys; "CryptoKeys"
0x18010b003  mov     [rbp+0EE0h+var_EA8], rax
0x18010b007  lea     rax, aCscfolder; "CSCFolder"
0x18010b00e  mov     [rbp+0EE0h+var_EA0], rax
0x18010b012  lea     rax, aDesktop; "Desktop"
0x18010b019  mov     [rbp+0EE0h+var_E98], rax
0x18010b01d  lea     rax, aDeviceMetadata; "Device Metadata Store"
0x18010b024  mov     [rbp+0EE0h+var_E90], rax
0x18010b028  lea     rax, aDocumentslibra; "DocumentsLibrary"
0x18010b02f  mov     [rbp+0EE0h+var_E88], rax
0x18010b033  lea     rax, aDownloads; "Downloads"
0x18010b03a  mov     [rbp+0EE0h+var_E80], rax
0x18010b03e  lea     rax, aDpapikeys; "DpapiKeys"
0x18010b045  mov     [rbp+0EE0h+var_E78], rax
0x18010b049  lea     rax, aFavorites; "Favorites"
0x18010b050  mov     [rbp+0EE0h+var_E70], rax
0x18010b054  lea     rax, aFonts; "Fonts"
0x18010b05b  mov     [rbp+0EE0h+var_E68], rax
0x18010b05f  lea     rax, aGames; "Games"
0x18010b066  mov     [rbp+0EE0h+var_E60], rax
0x18010b06d  lea     rax, aGametasks; "GameTasks"
0x18010b074  mov     [rbp+0EE0h+var_E58], rax
0x18010b07b  lea     rax, aHistory; "History"
0x18010b082  mov     [rbp+0EE0h+var_E50], rax
0x18010b089  lea     rax, aHomegroupcurre; "HomeGroupCurrentUserFolder"
0x18010b090  mov     [rbp+0EE0h+var_E48], rax
0x18010b097  lea     rax, aHomegroupfolde; "HomeGroupFolder"
0x18010b09e  mov     [rbp+0EE0h+var_E40], rax
0x18010b0a5  lea     rax, aImplicitappsho; "ImplicitAppShortcuts"
0x18010b0ac  mov     [rbp+0EE0h+var_E38], rax
0x18010b0b3  lea     rax, aLibraries; "Libraries"
0x18010b0ba  mov     [rbp+0EE0h+var_E30], rax
0x18010b0c1  lea     rax, aLinks; "Links"
0x18010b0c8  mov     [rbp+0EE0h+var_E28], rax
0x18010b0cf  lea     rax, aLocalAppdata; "Local AppData"
0x18010b0d6  mov     [rbp+0EE0h+var_E20], rax
0x18010b0dd  lea     rax, aLocalappdatalo; "LocalAppDataLow"
0x18010b0e4  mov     [rbp+0EE0h+var_E18], rax
0x18010b0eb  lea     rax, aLocalizedresou; "LocalizedResourcesDir"
0x18010b0f2  mov     [rbp+0EE0h+var_E10], rax
0x18010b0f9  lea     rax, aMapifolder; "MAPIFolder"
0x18010b100  mov     [rbp+0EE0h+var_E08], rax
0x18010b107  lea     rax, aMusiclibrary; "MusicLibrary"
0x18010b10e  mov     [rbp+0EE0h+var_E00], rax
0x18010b115  lea     rax, aMyMusic; "My Music"
0x18010b11c  mov     [rbp+0EE0h+var_DF8], rax
0x18010b123  lea     rax, aMyPictures; "My Pictures"
0x18010b12a  mov     [rbp+0EE0h+var_DF0], rax
0x18010b131  lea     rax, aMyVideo; "My Video"
0x18010b138  mov     [rbp+0EE0h+var_DE8], rax
0x18010b13f  lea     rax, aMycomputerfold; "MyComputerFolder"
0x18010b146  mov     [rbp+0EE0h+var_DE0], rax
0x18010b14d  lea     rax, aNethood; "NetHood"
0x18010b154  mov     [rbp+0EE0h+var_DD8], rax
0x18010b15b  lea     rax, aOemLinks; "OEM Links"
0x18010b162  mov     [rbp+0EE0h+var_DD0], rax
0x18010b169  lea     rax, aOriginalImages; "Original Images"
0x18010b170  mov     [rbp+0EE0h+var_DC8], rax
0x18010b177  lea     rax, aPersonal; "Personal"
0x18010b17e  mov     [rbp+0EE0h+var_DC0], rax
0x18010b185  lea     rax, aPhotoalbums; "PhotoAlbums"
0x18010b18c  mov     [rbp+0EE0h+var_DB8], rax
0x18010b193  lea     rax, aPictureslibrar; "PicturesLibrary"
0x18010b19a  mov     [rbp+0EE0h+var_DB0], rax
0x18010b1a1  lea     rax, aPlaylists; "Playlists"
0x18010b1a8  mov     [rbp+0EE0h+var_DA8], rax
0x18010b1af  lea     rax, aPrintersfolder; "PrintersFolder"
0x18010b1b6  mov     [rbp+0EE0h+var_DA0], rax
0x18010b1bd  lea     rax, aPrinthood; "PrintHood"
0x18010b1c4  mov     [rbp+0EE0h+var_D98], rax
0x18010b1cb  lea     rax, aProfile; "Profile"
0x18010b1d2  mov     [rbp+0EE0h+var_D90], rax
0x18010b1d9  lea     rax, aProgramfiles; "ProgramFiles"
0x18010b1e0  mov     [rbp+0EE0h+var_D88], rax
0x18010b1e7  lea     rax, aProgramfilesco; "ProgramFilesCommon"
0x18010b1ee  mov     [rbp+0EE0h+var_D80], rax
0x18010b1f5  lea     rax, aProgramfilesco_0; "ProgramFilesCommonX86"
0x18010b1fc  mov     [rbp+0EE0h+var_D78], rax
0x18010b203  lea     rax, aProgramfilesx8; "ProgramFilesX86"
0x18010b20a  mov     [rbp+0EE0h+var_D70], rax
0x18010b211  lea     rax, aPrograms; "Programs"
0x18010b218  mov     [rbp+0EE0h+var_D68], rax
0x18010b21f  lea     rax, aPublic; "Public"
0x18010b226  mov     [rbp+0EE0h+var_D60], rax
0x18010b22d  lea     rax, aPublicaccountp; "PublicAccountPictures"
0x18010b234  mov     [rbp+0EE0h+var_D58], rax
0x18010b23b  lea     rax, aPublicgametask; "PublicGameTasks"
0x18010b242  mov     [rbp+0EE0h+var_D50], rax
0x18010b249  lea     rax, aPubliclibrarie; "PublicLibraries"
0x18010b250  mov     [rbp+0EE0h+var_D48], rax
0x18010b257  lea     rax, aQuickLaunch; "Quick Launch"
0x18010b25e  mov     [rbp+0EE0h+var_D40], rax
0x18010b265  lea     rax, aRecent; "Recent"
0x18010b26c  mov     [rbp+0EE0h+var_D38], rax
0x18010b273  lea     rax, aRecordedtvlibr; "RecordedTVLibrary"
0x18010b27a  mov     [rbp+0EE0h+var_D30], rax
0x18010b281  lea     rax, aRecyclebinfold; "RecycleBinFolder"
0x18010b288  mov     [rbp+0EE0h+var_D28], rax
0x18010b28f  lea     rax, aResourcedir; "ResourceDir"
0x18010b296  mov     [rbp+0EE0h+var_D20], rax
0x18010b29d  lea     rax, aRingtones; "Ringtones"
0x18010b2a4  mov     [rbp+0EE0h+var_D18], rax
0x18010b2ab  lea     rax, aRoamedTileImag; "Roamed Tile Images"
0x18010b2b2  mov     [rbp+0EE0h+var_D10], rax
0x18010b2b9  lea     rax, aRoamingTiles; "Roaming Tiles"
0x18010b2c0  mov     [rbp+0EE0h+var_D08], rax
0x18010b2c7  lea     rax, aSavedgames; "SavedGames"
0x18010b2ce  mov     [rbp+0EE0h+var_D00], rax
0x18010b2d5  lea     rax, aScreenshots; "Screenshots"
0x18010b2dc  mov     [rbp+0EE0h+var_CF8], rax
0x18010b2e3  lea     rax, aSearches; "Searches"
0x18010b2ea  mov     [rbp+0EE0h+var_CF0], rax
0x18010b2f1  lea     rax, aSearchhomefold; "SearchHomeFolder"
0x18010b2f8  mov     [rbp+0EE0h+var_CE8], rax
0x18010b2ff  lea     rax, aSendto; "SendTo"
0x18010b306  mov     [rbp+0EE0h+var_CE0], rax
0x18010b30d  lea     rax, aStartMenu; "Start Menu"
0x18010b314  mov     [rbp+0EE0h+var_CD8], rax
0x18010b31b  lea     rax, aStartup; "Startup"
0x18010b322  mov     [rbp+0EE0h+var_CD0], rax
0x18010b329  lea     rax, aSynccenterfold; "SyncCenterFolder"
0x18010b330  mov     [rbp+0EE0h+var_CC8], rax
0x18010b337  lea     rax, aSyncresultsfol; "SyncResultsFolder"
0x18010b33e  mov     [rbp+0EE0h+var_CC0], rax
0x18010b345  lea     rax, aSyncsetupfolde; "SyncSetupFolder"
0x18010b34c  mov     [rbp+0EE0h+var_CB8], rax
0x18010b353  lea     rax, aSystem; "System"
0x18010b35a  mov     [rbp+0EE0h+var_CB0], rax
0x18010b361  lea     rax, aSystemcertific; "SystemCertificates"
0x18010b368  mov     [rbp+0EE0h+var_CA8], rax
0x18010b36f  lea     rax, aSystemx86; "SystemX86"
0x18010b376  mov     [rbp+0EE0h+var_CA0], rax
0x18010b37d  lea     rax, aTemplates; "Templates"
0x18010b384  mov     [rbp+0EE0h+var_C98], rax
0x18010b38b  lea     rax, aUserPinned; "User Pinned"
0x18010b392  mov     [rbp+0EE0h+var_C90], rax
0x18010b399  lea     rax, aUserprofiles; "UserProfiles"
0x18010b3a0  mov     [rbp+0EE0h+var_C88], rax
0x18010b3a7  lea     rax, aUserprogramfil_0; "UserProgramFiles"
0x18010b3ae  mov     [rbp+0EE0h+var_C80], rax
0x18010b3b5  lea     rax, aUserprogramfil; "UserProgramFilesCommon"
0x18010b3bc  mov     [rbp+0EE0h+var_C78], rax
0x18010b3c3  lea     rax, aUsersfilesfold; "UsersFilesFolder"
0x18010b3ca  mov     [rbp+0EE0h+var_C70], rax
0x18010b3d1  lea     rax, aUserslibraries; "UsersLibrariesFolder"
0x18010b3d8  mov     [rbp+0EE0h+var_C68], rax
0x18010b3df  lea     rax, aVideoslibrary; "VideosLibrary"
0x18010b3e6  mov     [rbp+0EE0h+var_C60], rax
0x18010b3ed  lea     rax, aWindows; "Windows"
0x18010b3f4  mov     [rbp+0EE0h+var_C58], rax
0x18010b3fb  lea     rax, a008ca0b155b44c; "{008ca0b1-55b4-4c56-b8a8-4de4b299d3be}"
0x18010b402  mov     [rbp+0EE0h+var_C50], rax
0x18010b409  lea     rax, a00bcfc5aEd944e; "{00BCFC5A-ED94-4e48-96A1-3F6217F21990}"
0x18010b410  mov     [rbp+0EE0h+var_C48], rax
0x18010b417  lea     rax, a0139d44e6afe49; "{0139D44E-6AFE-49F2-8690-3DAFCAE6FFB8}"
0x18010b41e  mov     [rbp+0EE0h+var_C40], rax
0x18010b425  lea     rax, a0482af6c08f14c; "{0482af6c-08f1-4c34-8c90-e17ec98b1e17}"
0x18010b42c  mov     [rbp+0EE0h+var_C38], rax
0x18010b433  lea     rax, a054fae614dd847; "{054FAE61-4DD8-4787-80B6-090220C4B700}"
0x18010b43a  mov     [rbp+0EE0h+var_C30], rax
0x18010b441  lea     rax, a0762d272C50a4b; "{0762D272-C50A-4BB0-A382-697DCD729B80}"
0x18010b448  mov     [rbp+0EE0h+var_C28], rax
0x18010b44f  lea     rax, a0ac0837cBbf845; "{0AC0837C-BBF8-452A-850D-79D08E667CA7}"
0x18010b456  mov     [rbp+0EE0h+var_C20], rax
0x18010b45d  lea     rax, a0d4c3db603a346; "{0D4C3DB6-03A3-462F-A0E6-08924C41B5D4}"
0x18010b464  mov     [rbp+0EE0h+var_C18], rax
0x18010b46b  lea     rax, a0f214138B1d34a; "{0F214138-B1D3-4a90-BBA9-27CBC0C5389A}"
0x18010b472  mov     [rbp+0EE0h+var_C10], rax
0x18010b479  lea     rax, a15ca69b330ee49; "{15CA69B3-30EE-49C1-ACE1-6B5EC372AFB5}"
0x18010b480  mov     [rbp+0EE0h+var_C08], rax
0x18010b487  lea     rax, a1777f76168ad4d; "{1777F761-68AD-4D8A-87BD-30B759FA33DD}"
0x18010b48e  mov     [rbp+0EE0h+var_C00], rax
0x18010b495  lea     rax, a18989b1d99b545; "{18989B1D-99B5-455B-841C-AB7C74E4DDFC}"
0x18010b49c  mov     [rbp+0EE0h+var_BF8], rax
0x18010b4a3  lea     rax, a190337d1B8ca41; "{190337d1-b8ca-4121-a639-6d472d16972a}"
0x18010b4aa  mov     [rbp+0EE0h+var_BF0], rax
0x18010b4b1  lea     rax, a1a6fdba2F42d43; "{1A6FDBA2-F42D-4358-A798-B74D745926C5}"
0x18010b4b8  mov     [rbp+0EE0h+var_BE8], rax
0x18010b4bf  lea     rax, a1ac14e7702e74e; "{1AC14E77-02E7-4E5D-B744-2EB1AE5198B7}"
0x18010b4c6  mov     [rbp+0EE0h+var_BE0], rax
0x18010b4cd  lea     rax, a1b3ea5dcB58747; "{1B3EA5DC-B587-4786-B4EF-BD1DC332AEAE}"
0x18010b4d4  mov     [rbp+0EE0h+var_BD8], rax
0x18010b4db  lea     rax, a1e87508d89c242; "{1e87508d-89c2-42f0-8a7e-645a0f50ca58}"
0x18010b4e2  mov     [rbp+0EE0h+var_BD0], rax
0x18010b4e9  lea     rax, a2112ab0aC86a4f; "{2112AB0A-C86A-4FFE-A368-0DE96E47012E}"
0x18010b4f0  mov     [rbp+0EE0h+var_BC8], rax
0x18010b4f7  lea     rax, a2400183a618549; "{2400183A-6185-49FB-A2D8-4A392A602BA3}"
0x18010b4fe  mov     [rbp+0EE0h+var_BC0], rax
0x18010b505  lea     rax, a24d89e242f1945; "{24D89E24-2F19-4534-9DDE-6A6671FBB8FE}"
0x18010b50c  mov     [rbp+0EE0h+var_BB8], rax
0x18010b513  lea     rax, a289a9a43Be4440; "{289a9a43-be44-4057-a41b-587a76d7e7f9}"
0x18010b51a  mov     [rbp+0EE0h+var_BB0], rax
0x18010b521  lea     rax, a2a00375e224c49; "{2A00375E-224C-49DE-B8D1-440DF7EF3DDC}"
0x18010b528  mov     [rbp+0EE0h+var_BA8], rax
0x18010b52f  lea     rax, a2b0f765dC0e941; "{2B0F765D-C0E9-4171-908E-08A611B84FF6}"
0x18010b536  mov     [rbp+0EE0h+var_BA0], rax
0x18010b53d  lea     rax, a2c36c0aa58124b; "{2C36C0AA-5812-4b87-BFD0-4CD0DFB19B39}"
0x18010b544  mov     [rbp+0EE0h+var_B98], rax
0x18010b54b  lea     rax, a31c0dd2594394f; "{31C0DD25-9439-4F12-BF41-7FF4EDA38722}"
0x18010b552  mov     [rbp+0EE0h+var_B90], rax
0x18010b559  lea     rax, a3214fab5975742; "{3214FAB5-9757-4298-BB61-92A9DEAA44FF}"
0x18010b560  mov     [rbp+0EE0h+var_B88], rax
0x18010b567  lea     rax, a339719b58c4748; "{339719B5-8C47-4894-94C2-D8F77ADD44A6}"
0x18010b56e  mov     [rbp+0EE0h+var_B80], rax
0x18010b575  lea     rax, a33e281304e1e46; "{33E28130-4E1E-4676-835A-98395C3BC3BB}"
0x18010b57c  mov     [rbp+0EE0h+var_B78], rax
0x18010b583  lea     rax, a352481e833be42; "{352481E8-33BE-4251-BA85-6007CAEDCF9D}"
0x18010b58a  mov     [rbp+0EE0h+var_B70], rax
0x18010b591  lea     rax, a374de290123f45; "{374DE290-123F-4565-9164-39C4925E467B}"
0x18010b598  mov     [rbp+0EE0h+var_B68], rax
0x18010b59f  lea     rax, a3b193882D3ad4e; "{3B193882-D3AD-4eab-965A-69829D1FB59F}"
0x18010b5a6  mov     [rbp+0EE0h+var_B60], rax
0x18010b5ad  lea     rax, a3d644c9b1fb84f; "{3D644C9B-1FB8-4f30-9B45-F670235F79C0}"
0x18010b5b4  mov     [rbp+0EE0h+var_B58], rax
0x18010b5bb  lea     rax, a3eb685db65f94c; "{3EB685DB-65F9-4CF6-A03A-E3EF65729F3D}"
0x18010b5c2  mov     [rbp+0EE0h+var_B50], rax
0x18010b5c9  lea     rax, a43668bf8C14e49; "{43668BF8-C14E-49B2-97C9-747784D784B7}"
0x18010b5d0  mov     [rbp+0EE0h+var_B48], rax
0x18010b5d7  lea     rax, a48daf80bE6cf4f; "{48DAF80B-E6CF-4F4E-B800-0E69D84EE384}"
0x18010b5de  mov     [rbp+0EE0h+var_B40], rax
0x18010b5e5  lea     rax, a491e922f56434a; "{491E922F-5643-4AF4-A7EB-4E7A138D8174}"
0x18010b5ec  mov     [rbp+0EE0h+var_B38], rax
0x18010b5f3  lea     rax, a4bd8d5716d1948; "{4BD8D571-6D19-48D3-BE97-422220080E43}"
0x18010b5fa  mov     [rbp+0EE0h+var_B30], rax
  ... truncated ...
```
